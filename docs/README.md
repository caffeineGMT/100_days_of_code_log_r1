---
title: 100 Days of Code - Round 1
description: by Maitao
#pg_bk_color: '#e6e8de'
#header_bk_color: '#1a7f6d'
#link_color: '#1a7f6d'
---

<!-- markdownlint-disable MD022 MD024 MD032 MD033 -->

# 100 Days of Code

<!-- <p class="toc"><a href="./index.html">&lt;– back to Table of Contents</a></p> -->

| Code Log | Start       | End               |
| -------- | ----------- | ----------------- |
| this log | Aug 4, 2020 | November 12, 2020 |

## Challenge & Commitment

This is part of Alexander Kallaway's [100DaysOfCode](https://github.com/Kallaway/100-days-of-code "the official repo") challenge. More details about the challenge can be found here: [100daysofcode.com](http://100daysofcode.com/ "100daysofcode.com").

**Commitment:** _I will code daily for the next 100 days._

| Start Date  | End Date          |
| ----------- | ----------------- |
| Aug 4, 2020 | November 12, 2020 |

## Goals

- [x] Code daily
- [ ] Finish Code with Mosh "Java" Series
- [ ] Finish Code with Mosh "React" Series
- [ ] Finish Udacity React Projects
- [ ] Finish Machine Learning Specialization

# Code Log

---

## 1. Java Iterable Interface

### Day 1: August 4th, 2020 - Tuesday

**Project:** Using Java Iterable interface

```java
public class GenericList<T> implements Iterable<T> {
    private T[] items = (T[]) new Object[10];
    private int count;

    public void add(T item) {
        items[count++] = item;
    }

    public T get(int index) {
        return items[index];
    }

    @Override
    public Iterator<T> iterator() {
        return new ListIterator(this);
    }

    private class ListIterator implements Iterator<T> {
        private GenericList<T> list;
        private int index = 0;

        public ListIterator(GenericList<T> list) {
            this.list = list;
        }

        @Override
        public boolean hasNext() {
            return index < list.count;
        }

        @Override
        public T next() {
            return list.items[index++];
            // return list.get[index++];
        }
    }
}
```

**Progress:**

- for each loop rely on the the iterable interface and using iterator internally to do iteration
- first we need to implement Iterable interface
- second we need to implement a Iterator interface to generate a iterator
- The reason why we use the private class for ListIterator here is that the generic type T can be passed down from the moment we create a GenericList

**Links:** [Solution repo](https://github.com/caffeineGMT/Java_Learning/blob/master/UltimateJava_Part3/src/com/codewithmosh/collections/GenericList.java)

---
