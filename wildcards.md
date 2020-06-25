## Wildcards
- Similar to placeholders
- Symbols that stand in for other characters
- Useful for searching for specific files / directories

List of results (and contents):		`$ ls ___ `
Info of resulting objects:  		`$ file ___`

`   ?     *     []   `


### Example list.txt
```
$ ls

Oad
Oarmeerrd
Obd
Ocd
Od
Odd
Oed
Oerd
Oereed
Oerererd
Oind
Okhd
```



### ?
- Matches single char

```
ls O??d

Oerd
Oind
Okhd
```

### *
- Matches single / multiple chars

```
ls O*d

Oad
Oarmeerrd
Obd
Ocd
Od
Odd
Oed
Oerd
Oereed
Oerererd
Oind
Okhd
```


### []
- Matches a set number of chars
- Still single

```
ls O[ac]d

Oad
Ocd
```

```
ls O[a-e]d

Oad
Obd
Ocd
Odd
Oed
```
