# Coding Standards

This section is ment to describe the L'Oréal Mex Data Science Team coding
standards.

---
## We use Python...

So we strongly encourage you to dive deep into the [zen of python](https://peps.python.org/pep-0020/).
In case you're not familiar with it, we kindly list it for you so you don't
miss it:

> _The Zen of Python, by Tim Peters_
>
> 1. _Beautiful is better than ugly._
> 2. _Explicit is better than implicit._
> 3. _Simple is better than complex._
> 4. _Complex is better than complicated._
> 5. _Flat is better than nested._
> 6. _Sparse is better than dense._
> 7. _Readability counts._
> 8. _Special cases aren't special enough to break the rules._
> 9. _Although practicality beats purity._
> 10. _Errors should never pass silently._
> 11. _Unless explicitly silenced._
> 12. _In the face of ambiguity, refuse the temptation to guess._
> 13. _There should be one --and preferably only one-- obvious way to do it._
> 14. _Although that way may not be obvious at first unless you're Dutch._
> 15. _Now is better than never._
> 16. _Although never is often better than *right* now._
> 17. _If the implementation is hard to explain, it's a bad idea._
> 18. _If the implementation is easy to explain, it may be a good idea._
> 19. _Namespaces are one honking great idea -- let's do more of those!_

!!! info
    You can always summon the zen of python with `import this` within a python
    script.

---
## Data transformations

Spoiler alert in case you're new to this gorgeous monster called Data Science,
you're going to be dealing with multiple datasets, joining tables, perfoming
data transformations, APIs, and in the particular case of L'Oréal,
data cleaning... TONS OF IT.

For this reason, as the 7° point of the zen of python suggests, readability counts.

### Method Concatenation

Avoid performing multiple data trasnformations in several steps unless you need
to explicitly store the results in memory.

!!! note
    In all following cases, the output dataframe is the same but the method
    concatenation style is more efficient handling memory and reads as an
    ordered sequence of transformations.

#### Pandas

Given the example dataframe:

|category|units|
|:--|:--|
|A|1|
|A|2|
|B|3|
|B|4|
|C|5|
|C|6|

Unclean common usage:

```python
df_group = df.groupby('category').agg(sum_units=('units', 'sum'))
df_group['units_squared'] = df_group['sum_units'] ** 2
df_group['prop'] = df_group['sum_units'] / df['sum_units'].sum()
```

Method Concatenation:

```python
df_group = (
    df
    .groupby('category')
    .agg(
        sum_units = ('units', 'sum'))
    .assign(
        units_squared = lambda df: df.sum_units ** 2,
        prop          = lambda df: df.sum_units / df.units_squared.sum()))
```



---
