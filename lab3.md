# Lab Report #3
## Jason Chang / jsc008@ucsd.edu
## CSE15L / Section A01
## May 10, 2023

Below is lab report #3 - Researching Commands (Week 5-6)

# Command

Command Chosen: `grep`.

## Way #1
Source: Found through [the Oracle filesearch documentation](https://docs.oracle.com/cd/E19253-01/806-7612/filesearch-99633/index.html).
One way to use the command `grep` is with `grep string file`, where `string` is the search key and `file` is the file that is being searched.
Example #1:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep PLANES chapter-1.txt```
This command searches for "PLANES" in `chapter-1.txt`. The output is `"WE HAVE SOME PLANES"`.

Example #2:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep Boarding chapter-1.txt```
This command searches for "Boarding" in `chapter-1.txt`. The output is `Boarding the Flights`.

This command is useful since it returns all the instances in which the string shows up.

## Way #2
Source: Found through [the Oracle filesearch documentation](https://docs.oracle.com/cd/E19253-01/806-7612/filesearch-99633/index.html).
Another way to use the command `grep` is with `grep string *`, where `string` is the search key.
Example #1:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep "Boston, and" *```
This command searches for "Boston, and" in ALL files in the `/911report` directory. The output is 
```chapter-6.txt:                United States, worked as a cabdriver in Boston, and sent money back to his fellow```
```chapter-8.txt:                attacks on London, Boston, and New York. Attorney General John Ashcroft was briefed```

Example #2:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep "boston" *```
This command searches for "boston" in ALL files in the `/911report` directory. There is no output, as it is case-sensitive.

This command is useful since it returns all the instances in which the string shows up in the whole directory, if you are not sure which file to look in.



## Way #3
Source: Found through [Hostinger tutorials](https://www.hostinger.com/tutorials/grep-command-in-linux-useful-examples/).
Another way to use the command `grep` is with `grep 'query1\|query2' file`, where `query1` and `query2` are the search keys and `file` is the file that is being searched.
Example #1:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep 'Ashcroft was briefed\|Other cities' *```
This command searches for BOTH `Ashcroft was briefed` and `Other cities` in the whole directory of `/911report`. The output is 
```chapter-2.txt:            Other cities with branches of al Khifa included Atlanta, Boston, Chicago, Pittsburgh,```
```chapter-8.txt:                attacks on London, Boston, and New York. Attorney General John Ashcroft was briefed```
```chapter-8.txt:            Attorney General Ashcroft was briefed by the CIA in May and by Pickard in early July```

Example #2:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep 'Ashcroft was briefed\|Other cities' chapter-8.txt```
This command searches for BOTH `Ashcroft was briefed` and `Other cities`; this time, only in `/911report/chapter-8.txt`. The output is 
```attacks on London, Boston, and New York. Attorney General John Ashcroft was briefed```
```Attorney General Ashcroft was briefed by the CIA in May and by Pickard in early July```

This command is useful compared to previous ones, as you can search for more than one keyword at once. This allows for more flexibility when searching for different capitalizations of a single word or phrase, for instance.


## Way #4
Source: Found through [Hostinger tutorials](https://www.hostinger.com/tutorials/grep-command-in-linux-useful-examples/).
Another way to use the command `grep` is with `grep '^query' file`, where `query` is the search key and `file` is the file that is being searched.
Example #1:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep '^N' chapter-1.txt```
This command searches for lines that start with `N` in `/chapter-1.txt`. The output is 
```NORAD Mission and Structure. NORAD is a binational command established in 1958 between the United States and Canada. Its mission was, and is, to defend the airspace of North America and protect the continent. That mission does not distinguish between internal and external threats; but because NORAD was created to counter the Soviet threat, it came to define its job as defending against external attacks.```
```NATIONAL CRISIS MANAGEMENT```

Example #2:
```root@XPS:/***/CSE12/docsearch/technical/911report# grep '^A' *```
This command searches for lines that start with `A` in the whole directory of `/911report`. The output is 
```chapter-1.txt:American Airlines Flight 11```.

This command is useful compared to previous ones, as you can search specifically for lines that start with a string or phrase. This increases the specificity in which someone looking for a specific string in the file can use. In particular, this can be used for things like headers or titles.
