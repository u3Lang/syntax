# u3Lang Syntax Specification
Sat Mar 18 01:32:33 CET 2023
-----------------------------

Task
## Design and Implement a general-purpose, statically-typed programming language with certain useful data types built-in and some within a standard library  
U3 means [universal, useful, usable]

## To consider
expressions only, default return value – result


## Syntax

0. Case-insensitive
1. Reserved words(tokens): no, yes, if, el, elif
2. Built-in Types and Variable Initialization
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  0 | boolean | is${variableName} | prefix  | :bool | | 
  
  Declaration and initialization:  
  ```
  isCompleted = yes
  isEven = no
  ```
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  1 | string | N/A | postfix | :string | the default type for any variable that doesn't have a marker specified | 
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  2 | number | # | postfix | :number, :d64, :i32, :ui32, etc |  | 
  
  Declaration and initialization:  
  ```
  ``` 

  \# | Type Name      | Identifier Type Indicator | Placement | Arguments | Explicit Type Identifier
  | -| -| -| -| -| -|
  3 | date | * | postfix | :date | | 
  
  Declaration and initialization:  
  ```
  ``` 

  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  4 | url | @ | postfix | :url | | 
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  5 | id | ^ | postfix | :uuid | | 
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  6 | custom type | % | postfix | :${name-of-the-custom-type} | i. e. the same syntax as in TypeScript (and Kotlin) | 
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  7 | preciseNumber | ## | postfix | :preciseNumber |  | 
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  8 | encrypted | ${sourceDataType}~   | postfix | :${sourceDataType}Encrypted | | `anEcryptedString~ = ``secretValue```, `aNumber#~`, `aDate*~` 
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  9 | currencyAmount | $${currencyName}     | postfix | :currencyAmount:${currencyName} | | `monthlyWage$USD`, `vatFee$EUR`
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  10| location | _ | postfix | :location | | `home_`, `office_`
  
  Declaration and initialization:  
  ```
  ``` 
  
  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  11| typed key-value pair | > | infix | :pair | Represents a key-value pair. | `id^>user%` 
  
  Declaration and initialization:  
  ```
  ``` 

  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  12| result | ? | postfix | :result |  | `id^>user%` 
  
  Declaration and initialization:  
  ```
  ``` 

  \# | Type Name      | Identifier Type Indicator | Placement | Explicit Type Identifier
  | -| -| -| -| -|
  13| state | ... | postfix | :state | 

  Declaration and initialization:  
  ```
  toPerpare, toStart, toResume, toFinish, finished
  ``` 

1. All expressions should be surrounded by ()
   [result] is a default return type (returned from an expression which doesn't have a return type specified)

2. [] If-el, elif
   if () {

   } elif {

   } el {

   }

3. [] Function 
  doBar() {}

1. [] Abstract function
  doFoo?()

1. Anonymous function 

2. [] Overriding function
  doFoo!()

1. [] Generic function

2. [] Type
   ```
   newType% {}
   ```

   Creating instance of type
   ```
   newInstance% = declaredType%()
   ```


9.  [] Call on an instance
    `.`

10. [] Abstract Type
    Abstract types can not be extended (being inherited from), only implemented

11. [] Generic type 

12. [] List

13. [] Set (probably as a particular case of list)

14. [] For-loop


``` typescript
u3LangConfig: {
  compileTime: {
    types: {
      // avoid having much customization here since it increases the chance of having 
      // a source-code-compatibility headache
    }
  },
  runTime: {
    encryption: {
      algorithm: ``
      keysPath: ``
    }
    targetLanguage: `` // for transpiling
    targetPlatform: `` // for creating a binary executable
  }
}
```

<!-- 
Declaration and initialization:  
```
``` 
-->
