---
title: "Awk"
date: 2020-05-22T19:26:42-04:00
draft: false
toc: true
thumbnail: "linux-downloads.png"
categories:
  - "Terminal Tools"
tags:
  - "Awk"
---

Awk is a powerful language mainly for data extraction.  My main use has been to extract specific records or fields from large data set files before further analyzing in Excel or other text editors.  Some data sets I have worked with have been so large that Excel is unable to load the data set, which has required initial data extraction by either extracting only the required combination of records or fields of the data set.

I will be collecting various awk command examples as I run into the need to create them.  Awk is a powerful language for extracting and manipulating data text files. Several examples include function similar to using grep, separating columns of data, printing only certain columns or performing aggregate functions.

### Printing Columns

Awk command to print columns from a file. -F "," defines the column separator. $1 determines the field position you want to print.  $0 will print the entire row  of data.

```html
awk -F "," '{print $1}' poplation_by_zipcode
```

### Subtracting Values

Awk command for subtracting previous value from current value to return difference.

```html
awk -F "," '{if($2 == 24014) {print $1, $2, $3}}' poplation_by_zipcode.csv | awk 'NR==1{p=$3;next}{print $1, $2, $3, $3-p; p=$3}END{print p}'
```
#### Example Source Data:

| Report Date |	ZIP Code | Population |
| ----------- | --------- | --------------- |
| 08/21/2020  |	24014	   | 15              |
| 08/22/2020  |	24014	   | 16              |
| 08/23/2020  |	24014	   | 16              |
| 08/24/2020  |	24014	   | 16              |
| 08/25/2020  |	24014	   | 17              |
| 08/26/2020  |	24014	   | 17              |
| 08/27/2020  |	24014	   | 17              |
| 08/28/2020  |	24014	   | 17              |

#### Resulting Output of awk command:

| Report Date |	ZIP Code | Population | Difference |
|----------- | --------- | --------------- | ---------- |
| 08/21/2020  |	24014	   | 15              | 0          |
| 08/22/2020  |	24014	   | 16              | 1          |
| 08/23/2020  |	24014	   | 16              | 0          |
| 08/24/2020  |	24014	   | 16              | 0          |
| 08/25/2020  |	24014	   | 17              | 1          |
| 08/26/2020  |	24014	   | 17              | 0          |
| 08/27/2020  |	24014	   | 17              | 0          |
| 08/28/2020  |	24014	   | 17              | 0          |

### Adding Line Number
```html
awk '{print NR" "$0}' file.txt
```

#### Example Source Data:

$cat file.txt\
First Line of file\
Another line in file\
This is a last line in file

#### Resulting Output of awk command:
awk '{print NR" "$0}' file.txt\
1 First Line of file\
2 Another line in file\
3 This is a last line in file


