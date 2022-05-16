---
layout: post
status: publish
published: true
title: "GIT Tip: Git Grep Terms Across Multiple Lines in Files"
---
A small GIT tip: when you want to find a file where multiple terms can occur spread across multiple lines.

Git grep is an awesome tool in your toolbox: it is blazingly fast at finding stuff and pretty flexible it turns out.

Java (and other programming languages) will often split a line of code across multiple lines because our common width 
of files typically doesn't exceed 120 characters in editors. So you get split constructor calls, or using the stream API
you want to all places where you sort and make the results unique:

```java
people.stream()
    .distinct()
    .sorted(Comparator.comparing(Person::getLastName)
    .collect(Collectors.toList());
```

If you want to find this, a naive attempt would be to search for these terms directly:

```bash
% git grep -e "distinct()" --and -e "sorted("
```
But this will only find files that have the terms `distinct()` and `sorted(` on a single line, and that is not what we want.
Fortunately git grep has a solution for that: `--all-match` in combination with `--or`:

```bash
% git grep --all-match -e "distinct()" --or -e "sorted("
```

This will find all files that have a line with `distinct()` **or** `sorted(`.
