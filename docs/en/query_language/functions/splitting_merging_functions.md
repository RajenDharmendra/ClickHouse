# Functions for splitting and merging strings and arrays

## splitByChar(separator, s)

Splits a string into substrings separated by 'separator'.'separator' must be a string constant consisting of exactly one character.
Returns an array of selected substrings. Empty substrings may be selected if the separator occurs at the beginning or end of the string, or if there are multiple consecutive separators.

**Example:**

```sql
SELECT splitByChar(',', '1,2,3,abcde')
```
```text
┌─splitByChar(',', '1,2,3,abcde')─┐
│ ['1','2','3','abcde']           │
└─────────────────────────────────┘
```

## splitByString(separator, s)

The same as above, but it uses a string of multiple characters as the separator. If the string is empty, it will split the string into an array of single characters.

**Example:**

```sql
SELECT splitByString(', ', '1, 2 3, 4,5, abcde')
```
```text
┌─splitByString(', ', '1, 2 3, 4,5, abcde')─┐
│ ['1','2 3','4,5','abcde']                 │
└───────────────────────────────────────────┘
```

```sql
SELECT splitByString('', 'abcde')
```
```text
┌─splitByString('', 'abcde')─┐
│ ['a','b','c','d','e']      │
└────────────────────────────┘
```

## arrayStringConcat(arr\[, separator\])

Concatenates the strings listed in the array with the separator.'separator' is an optional parameter: a constant string, set to an empty string by default.
Returns the string.

## alphaTokens(s)

Selects substrings of consecutive bytes from the ranges a-z and A-Z.Returns an array of substrings.

**Example:**

```sql
SELECT alphaTokens('abca1abc')
```
```text
┌─alphaTokens('abca1abc')─┐
│ ['abca','abc']          │
└─────────────────────────┘
```
[Original article](https://clickhouse.tech/docs/en/query_language/functions/splitting_merging_functions/) <!--hide-->
