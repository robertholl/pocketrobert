---
title: "Awk"
date: 2020-05-22T19:26:42-04:00
draft: false
thumbnail: ""
categories:
  - "Awk"
tags:
  - "Awk`"
menu:
    main:
      name: "Awk"
      weight: 10
---

# Awk Introduction

I will be collecting various awk command examples as I run into the need to create them.  Awk is a powerful language for extracting and manipulating data text files. Several examples include function similar to using grep, separating columns of data, printing only certain columns or performing aggregate functions.

Awk command for subtracting value from previous value to return difference.

```html
awk -F "," '{if($2 == 22625) {print $1, $2, $3}}' VDH-COVID-19-PublicUseDataset-ZIPCode.csv | awk 'NR==1{p=$3;next}{print $1, $2, $3, $3-p; p=$3}END{print p}'
```
### Example Source Data:

| Report Date |	ZIP Code | Number of Cases |
| ----------- | --------- | --------------- |
| 08/21/2020  |	22625	   | 15              |
| 08/22/2020  |	22625	   | 16              |
| 08/23/2020  |	22625	   | 16              |
| 08/24/2020  |	22625	   | 16              |
| 08/25/2020  |	22625	   | 17              |
| 08/26/2020  |	22625	   | 17              |
| 08/27/2020  |	22625	   | 17              |
| 08/28/2020  |	22625	   | 17              |

### Resulting Output of awk command:

| Report Date |	ZIP Code | Number of Cases | Difference |
|----------- | --------- | --------------- | ---------- |
| 08/21/2020  |	22625	   | 15              | 0          |
| 08/22/2020  |	22625	   | 16              | 1          |
| 08/23/2020  |	22625	   | 16              | 0          |
| 08/24/2020  |	22625	   | 16              | 0          |
| 08/25/2020  |	22625	   | 17              | 1          |
| 08/26/2020  |	22625	   | 17              | 0          |
| 08/27/2020  |	22625	   | 17              | 0          |
| 08/28/2020  |	22625	   | 17              | 0          |
