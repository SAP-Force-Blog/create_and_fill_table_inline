# Create, set type and fill a table using just one command

First, take a look at this code

```ABAP
data(lt_values) = value vrm_values(
  ( key = 'KEY01' text = 'Lorem ipsum dolor sit amet,'  )
  ( key = 'KEY02' text = 'consectetur adipiscing elit.' )
  ( key = 'KEY03' text = 'Suspendisse fermentum'        )
  ( key = 'KEY04' text = 'nulla in porta.'              )
  ( key = 'KEY05' text = 'Nulla facilisi.'              )
  ( key = 'KEY06' text = 'Aliquam diam dui,'            )
  ( key = 'KEY07' text = 'gravida et erat at,'          )
  ( key = 'KEY08' text = 'pretium facilisis justo.'     )
  ( key = 'KEY09' text = 'Curabitur mollis turpis et'   )
  ( key = 'KEY10' text = 'nibh rutrum mollis.'          )
  ( key = 'KEY11' text = 'Integer eget tortor'          )
  ( key = 'KEY12' text = 'condimentum.'                 )
).
```

'data' is declaring a variable; 'value' is setting the type of it; A parentheses is a row of the table.

At the end you'll get a table filled with your values without having to declare a table and workarea and use the append command to fill it up.

You can also append a row without losing current table rows.

Use the 'base' command inside 'value' like this

```ABAP
" value type( base itab (...) )

lt_values = value #( base lt_values
  ( key = 'KEY13' text = 'Continue Lorem Ipsum,' )
  ( key = 'KEY14' text = 'and blah blah blah.'   )
).
```

Note that I've used the '#' symbol to dynamically pass the type because I already declared this table so there's no need to fill the type again.
