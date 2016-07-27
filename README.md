# CPP-SQL-FUZZER

Tables of allowed symbols in different inputs of SQL expression, result of parsing fuzz tables.
Contribution is highly welcomed.

## MySQL
| Injection | Allowed symbols |
|---|---|
| -1 union:  |  `., %.0, %"", %'', &.0, &\N, -.0, =\N, <0., >0., e0, ^0., |"", |'', |.0, |\N` |
| select 1:  |  `+-!~, !>, !<, !., !@, !~, -@, @|, @*, @=, @/, @^, @%, @>, @<, ~-, ~@, ~., ""$, ""/, ""a, ""=, ''*, ''<, ''>, ''_, +@+, @$%, @&&, @*., @=~, @<., @%C0%, @%C0/, @%FF|, \N$, \N%FF` |
| column from:  |  ``` ``, '', "", 1., 1e1, 1.1, %"", %'', .1, %\N, *"", *'', =.0, <.0, >.0, ="", ='', ^"", |"", |'' ``` |
| from table:  |  `.%20, %20.` |
| table limit:  |  ``` `` ``` |

## MSSQL  
| Injection | Allowed symbols |
|---|---|
| Any place | `%00, %01, %02, %03, %04, %05, %06, %07, %08, %09, %0A, %0B, %0C, %0D, %0E, %0F, %10, %11, %12, %13, %14, %15, %16, %17, %18, %19, %1A, %1B, %1C, %1D, %1E, %1F, %20` |
| -1 union  | `., e, *0, %1, *\, -0, -\, ^0, |0, %C2%85, %C2%A0, [no whitespace]` |
| union select |  `%C2%85, %C2%A0`   |
|  select null | `-, ~, \/, \*, \ABC, \%, \#, \_, %C2%85, %C2%A0, ''#, ''_, %2B` |
|  column from | `'a'=\` |
|  from table | `.` |

