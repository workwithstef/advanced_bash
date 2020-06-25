###What is sort?

Sort is an external command that concatenates files while sorting their contents according to a sort type and writes results of sort to standard output.



###Sorting
Sort comes with 5 different types of sorting. Here is examples showing each sort type with associated options.



Numeric sort (general)     -->     	`-g / –general-numeric-sort
									general-numeric
									support for scientific notation
									0.1234e4 = 1234`


Numeric sort (human)       -->     	`-h / –human-numeric-sort
									human-numeric
									1.234K = 1234`


Numeric						-->		`-n / –numeric-sort
									numeric
									… < -1 < 0 < 1 < …`


Month 						-->		`-M / –month-sort
									month
									Unknown < Jan < Feb < … < Nov < Dec`


Random 						-->		`-r / –random-sort
									random`


Version 					-->		`-V / –version-sort
									version`

Note that each type of sort has a long option ending with -sort. In addition to specific sort options, the –sort=WORD option may be used to sort by word. For example –sort=random may be used in place of –random-sort or -r.





##Example 1 - Sorting names
Sort has no issues sorting lines alphabetically. Consider a list of famous people not sorted.

###Function

`famous-people()
{
curl --silent https://www.biographyonline.net/people/famous-100.html
| grep post-content | sed -e 's/<[^>]*.//g' -e 's/WWII//g' -e 's/\(Wilbur\)
/\1 Wright/'| grep -o -e '\(\([A-Z]\+[.]\?\)\+[a-z]*\s\)\+([0-9]\+\s[^)]\+.'
}`

###Command line

`famous-people | sort`

###Output

`Stephen King (1947 – )
Steve Jobs (1955 – 2012)
Sting (1951 – )
Tiger Woods (1975 – )
Tom Cruise (1962 – )
Usain Bolt (1986 – )
Vinci (1452 – 1519)
Walt Disney (1901 – 1966)
Wilbur Wright (1867 – 1912)
Woodrow Wilson (1856 – 1924)`


##Example 2 - General numeric sort
If we need to sort numeric values taking into fact scientific notation such as 99e2, we can use general numeric sort.

###Function

`unsorted-numeric-values ()
{
seq 100 | sort --random-sort | sed '3i 9e2' | sed '3i 99K'
}`

Consider the sorted output using each method. Note that in addition to containing values 1 through 100, the list also includes ‘9e12′ (900) and ’99K’ (99000).

###Command line

`unsorted-numeric-values | sort -n`

###Output

`96
97
98
99
99K
100`

What about 900 and 99000. That’s right it’s just numeric sort.



####Example 3 - Month sort

Month sort allows you to order lines by month. It could prove useful for grouping lines together by month especially in the case that the option of sorting by time is not available.

###Function

`months ()
{
cat  <<EOF
Jan
Aug
Mar
Apr
May
Jun
Dec
Feb
Sep
Oct
Nov
Jul
EOF
}`

###Command line
`months | sort --random-sort | sort --month-sort`

###Output

`Jan
Feb
Mar
Apr
May
Jun
Jul
Aug
Sep
Oct
Nov
Dec`
