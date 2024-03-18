# Coercion Edge Cases

|      Input                   |       ToString          |
|------------------------------|-------------------------|
| null                         | "null"                  |
| undefined                    | "undefined"             |
| true                         | "true"                  |
| false                        | "false"                 |
| 3.14159                      | "3.14159"               |
| 0                            | "0"                     |
| -0                           | "0"                     |
|                              |                         |
| []                           | ""                      |
| [1,2,3]                      | "1, 2, 3"               | 
| [null, undefined]            | ","                     |
| [[], [], []]                 | ",,,"                   |
| [,,,,]                       |",,,"                    |
|                              |                         |
| {}                           | "[object Object]"       |
| {a:2}                        | "[object Object]"       |
| {toString(){return "X";}}    | "X"                     |


|        Input                 | ToNumber                |
|------------------------------|-------------------------|
| false                        | 0                       |
| true                         | 1                       |
| null                         | 0                       |
| undefined                    | NaN                     |
|                              |                         |
| ""                           | 0                       |
| "0"                          | 0                       |
| "-0"                         | -0                      |
| " 009"                       | 9                       |
| "3.14159"                    | 3.14159                 |
| ".0"                         | 0                       |
| "0."                         | 0                       |
| "."                          | NaN                     |
| "0xaf"                       | 175                     |
|                              |                         |
| [""]                         | 0                       |
| ["0"]                        | 0                       |
| ["-0"]                       | -0                      |
| [null]                       | 0                       |
| [undefined]                  | 0                       |
| [1, 2, 3]                    | NaN                     |
| [[[]]]                       | 0                       |
|                              |                         |
| {..}                         | NaN                     |
| (valueOf() {return 3;})      | 3                       |
               

| Input                        | ToBoolean               | 
|------------------------------|-------------------------|
| ""                           | false                   |
| 0                            | false                   |
| -0                           |                         |
| null                         |                         |
| NaN                          |                         |
| false                        | false                   |
| undefined                    | undefined               |


| Input                        | Number()                |
|------------------------------|-------------------------|
| Number( "" );                | 0                       |
| Number( " \t\n" );           | 0                       |
| Number( null );              | 0                       |
| Number( undefined );         | NaN                     |
| Number( [] );                | 0                       |
| Number( [1,2,3] );           | NaN                     |
| Number( [null] );            | 0                       |
| Number( [undefined] )        | 0                       |
| Number( {} );                | NaN                     |


| Input                        | String()                |
|------------------------------|-------------------------|
| String( -0 );                | "0"                     |
| String( null );              | "null"                  |
| String( undefined );         | "undefined"             |
| String( [null] );            | ""                      |
| String( [undefined] );       | ""                      |


| Input                        | Boolean()               |
|------------------------------|-------------------------|
| Boolean(new Boolean(false)); | true                    |
