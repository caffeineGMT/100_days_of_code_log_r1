---
title: 100 Days of Code Round 1
description: by Maitao Guo
# pg_bk_color: "#e6e8de"
# header_bk_color: "#1a7f6d"
# link_color: "#1a7f6d"
---

<!-- markdownlint-disable MD022 MD024 MD032 MD033 -->

# Description

<p class="toc"><a href="./index.html">&lt;– back to Table of Contents</a></p>

| Code Log | Start       | End               |
| -------- | ----------- | ----------------- |
| this log | Aug 4, 2020 | November 12, 2020 |

## Challenge & Commitment

Challenge: This is part of Alexander Kallaway's [100DaysOfCode](https://github.com/Kallaway/100-days-of-code "the official repo") challenge. More details about the challenge can be found here: [100daysofcode.com](http://100daysofcode.com/ "100daysofcode.com").

Commitment: I will code daily for the next 100 days.

| Start Date  | End Date          |
| ----------- | ----------------- |
| Aug 4, 2020 | November 12, 2020 |

## Goals

- [x] Code daily
- [ ] Finish Code with Mosh "Java" Series
- [ ] Finish Code with Mosh "React" Series
- [ ] Finish Udacity React Projects
- [ ] Finish Machine Learning Specialization

---

# Code Log

## Day 2. Java Interface reference variable

### August 5th, 2020 - Wednesday

**Project Description:** It is confusing to see statement below:

`Printable objParent = new Parent();` where Printable is an interface, Parent implement it. But when creating a reference variable, we create an interface type and assign it to a class instance which implement the interface.

The complete code snippet is below:

```java
public class OverridenClass
{
    public static void main(String[] args)
    {
     Printable objParent = new Parent();
     objParent.sysout();
     objParent.displayName();
    }
}

interface Printable
{
    void sysout();
}

class Parent implements Printable
{
    public void displayName()
    {
     System.out.println("This is Parent Name");
    }

    public void sysout()
    {
        System.out.println("I am Printable Interface in Parent Class");
    }
}
```

**Notes:**

- Interface is like a class, but no concrete implementation. Other than that, they are very much alike when using.
- Interface type is like abstract method, force whoever implement it to provide concreted implementation
- The Printable Interface is like the parent class of Parent class. So when using Printable interface reference type to assign to an instance, this instance can only access the method belongs to the Printable Interface portion. In this case, it can only access sysout() method.

**Links:**

- see [stackoverflow question](https://stackoverflow.com/questions/14997202/creating-object-with-reference-to-interface)
- see [Oracle doc](https://docs.oracle.com/javase/tutorial/java/IandI/interfaceAsType.html)

## Day 1. Java Iterable Interface

### August 4th, 2020 - Tuesday

**Project Description:** trying to understand Java Iterable and Iterator interface

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

**Notes:**

- for each loop rely on the the iterable interface and using iterator internally to do iteration
- first we need to implement Iterable interface
- second we need to implement a Iterator interface to generate a iterator
- The reason why we use the private class for ListIterator here is that the generic type T can be passed down from the moment we create a GenericList

**Links:** [Solution repo](https://github.com/caffeineGMT/Java_Learning/blob/master/UltimateJava_Part3/src/com/codewithmosh/collections/GenericList.java)

---