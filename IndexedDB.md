# IndexedDB

## IndexedDB Structure
```
└── Origin
      ├── Database
      │     ├── Object Store
      │     │      ├── Object
      │     │      ├── Object
      │     │      ├── Object
      │     │      └── Object
      │     │      
      │     └── Object Store
      │            ├── Object
      │            └── Object
      │
      │
      └── Database
            ├── Object Store
            │      └── Object
            │      
            └── Object Store
                   ├── Object
                   ├── Object
                   └── Object
```

- On each object store we can have different types of objects, but it is not recommended. Better practice is to have some pattern.

## IndexedDB working scheme

```
├── Open a IndexedDB database with 'name' and 'version number'.
      └── Does it exist with that 'name'.
            ├── No:
            │    ├──Upgrade event.
            │    └── Success.
            │
            └── Yes:
                 └── Is the 'version number' greater than the browser version?
                         ├── Yes:
                         │    ├──Upgrade event.
                         │    └── Success.
                         │
                         └── No:
                              └── Is the 'version number' equal to the browser version?
                                      ├── Yes:
                                      │    └── Success.
                                      └── No: 
                                           └── Error!
```


## Keys for Data Stores

|Key Path (keyPath)   | Key Generator  | Description                                                                                  |
|---------------------|----------------|----------------------------------------------------------------------------------------------|
| No                  | No             | Value: It can hold any kind of value (like primitive values). We must supply a separare key argument whenever we want to add a new value. |
| Yes                 | No             | Value : only JS objects. The objects must have a property with the name 'name' as a key path.|
| No                  | Yes            | Value : any kind. Key: generated automatically, or we can supply a separate key argument.    |
| Yes                 | Yes            | Value : only JS objects. Usually a key is generated in the object in a property with the same name as a key path. However, if such property already exists, the value of that property is used as key, rather generating a new key. |