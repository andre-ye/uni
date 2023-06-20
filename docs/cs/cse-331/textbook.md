---
layout: default
title: Textbook Notes
parent: CSE 331
grand_parent: Computer Science
nav_order: 2
---

# Textbook Notes -- *Effective Java*
{: .no_toc }

CSE 331
{: .fs-6 .fw-300 }

---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## Preface

## Chapter 2: Creating and Destroying Objects

### Item 1: Consdier static factory methods instead of constructors
- A class can provide a public static facotry method: a static method that returns an instane of a class
- Alternative to a public constructor
- Advantages
    - Static factory methods have names
    - You can have multiple static factory methods
    - Not required to create a new object when they are invoked -- strict control over which instances exist
    - Can return a subtype of the return type
    - Class of return object can vary as a function of input parameters
    - Class of return object does not have to exist when the class containing the method is written
- Limitations
    - Classes without public or protected constructors cannot be subclassed
    - Hard for programmers to find (don't stand out in documentation)

### Item 2: Builder instead of constructor parameters
- Telescoping constructor pattern: one constructor with required parameters, one with single optional param, one with two, etc. This is really ugly. ewewewewew
- JavaBeans pattern: call a parameterless constructor to create the object, then use setter methods.
    - Easy but wordy to create new instances
    - JavaBean may be in an inconsistent state -- no way of enforcing construction
    - JavaBeans pattern does not allow for the class to be immutable
- Builder pattern: call a constructor with all of the required parameters nand get a builder object; setter methods to fill in the remaining optional parameters.

```java
// Builder Pattern
public class NutritionFacts {
    private final int servingSize;
    private final int servings;
    private final int calories;
    private final int fat;
    private final int sodium;
    private final int carbohydrate;

    public static class Builder {
        // Required parameters
        private final int servingSize;
        private final int servings;
        // Optional parameters - initialized to default values
        private int calories = 0;
        private int fat = 0;
        private int sodium = 0;
        private int carbohydrate = 0;
        public Builder(int servingSize, int servings) {
            this.servingSize = servingSize;
            this.servings = servings;
        }
        public Builder calories(int val)
            { calories = val; return this; }
        public Builder fat(int val)
            { fat = val; return this; }
        public Builder sodium(int val)
            { sodium = val; return this; }
        public Builder carbohydrate(int val)
            { carbohydrate = val; return this; }
        public NutritionFacts build() {
            return new NutritionFacts(this);
        }
    }

    private NutritionFacts(Builder builder) {
        servingSize = builder.servingSize;
        servings = builder.servings;
        calories = builder.calories;
        fat = builder.fat;
        sodium = builder.sodium;
        carbohydrate = builder.carbohydrate;
    }
}

NutritionFacts cocaCola = new NutritionFacts.Builder(240, 8).calories(100).sodium(35).carbohydrate(27).build();
```

- Advantages
    - Simulates named optional params in Python and Scala
    - Can perform validity checks
    - Well suited to class hierarchies

### Item 3: Enforce the singleton property with a private constructor or an enum type
- Singleton: a class which is instantiated only once.
    - Usually a stateless object
- Final field method
    - `public static final Elvis INSTANCE = new Elvis();`
    - Private constructor called once to initialize public static final field `Elvis.INSTANCE`
    - Lack of nonprivate constructor guarantees only one `Elvis` instance
- Static factory method
    - Public member is a static factory method, all calls to `Elvis.getInstance` return the same object reference
    - API makes it clear the class is a singleton
    - Public static field is final so contains the same object reference
    - Simpler
    - Flexibility to change your midn about if the class is a singleton without changing its API


### Item 5: Prefer dependency injection to hardwiring resources
- Classes often depend on underlying resources. These are often impelmetned as static utility classes or isngletons -- both inflexible and untestable. 
    - Inappropriate for classes whose behaviors are parameterized by an underlying resource
- Dependency injection: dictionary is a dependency of a spell checker and injected into the spell checker when it is created

### Item 6: Avoid creating unnecessary objects
- Youc an reuse a single object instead of creating an equivalent one every time it is needed.
- Autoboxing: mix primitive and boxed primitive types
- Prefer primitives to boxed primtiives; watch out for unintentioanl autoboxing
- 

## Chapter 2





