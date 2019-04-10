# Programming as Conversation Part 4: Introduction

## Learning Goals

- Compare collection data types to scalar data types
- Define `Array`
- Define `Array` element
- Define `Array` index
- Define `Hash`
- Define `Hash` key
- Define `Hash` value
- Demonstrate nesting of collection data structures

## Introduction

Thus far, we've been storing simple data in our variables, constant scalar
values: `String`s, `Integer`s, and `Float`s, etc. Learning to store and to work
with the data held in data structures will be the focus of this module.

## Compare Collection Data Types to Scalar Data Types

`String`s, `Integer`s, and `Float`s are scalar data types, they can be put on a
scale. A collection type holds multiple pieces of data and allows us to talk
about the collection as an _abstraction_.

This is very natural in conversation: we know "The Beatles" refer to four guys
from Liverpool. The "Gryffindors" collection of J.K. Rowling's "Wizarding World"
refer to a group of legal minors with a predilection for peril. How can we
represent collections in Ruby? By using `Arrays` and `Hashes` and "nesting"
them within one another.

## Define `Array`

An `Array` is a collection data type that holds multiple pieces of data under a
collected bare-word name whose members can be read and updated by using an
_index_.

Arrays are like tables that have an identifier that is an `Integer` that starts
at 0 and goes on up from there. You can think of them as being like a table.

**The Beatles**

|Index|Data|
|-----|----|
| 0   | "John Lennon"     |
| 1   | "Paul McCartney"  |
| 2   | "Ringo Starr"     |
| 3   | "George Harrison" |

To define this "table" in Ruby we would type (and you should test out in
IRB!):

```ruby
the_beatles = [ "John Lennon", "Paul McCartney", "Ringo Starr", "George Harrison"]
```
You provide a name, an assignment operator and then a list of data, separated
by commas, that should go in the `Array`, wrapped in `[]`. Each bit of
information is often a scalar value, but it could also be another collection,
more on that later.

## Define Array Element / Member

The individual pieces of data inside an `Array` are called _elements_. Some
people also call the _members_. In a collection of `the_beatles`, the `String`
`"George Harrison"` is an _element_.

## Define Array Index

Arrays provide a pointer to each _member_ called an index. The index for the
_element_ `"Ringo Starr"` is `2`.

## Define `Hash`

An `Hash` is a collection data type that holds multiple pieces of data under a
collected bare-word name whose members can be read and updated by using a
_key_. You can think of them as being like a table that looks like this:


|Key|Value|
|-----|----|
| :liverpool  | "The Beatles"     |
| :manchester | "The Smiths"  |
| :coventry   | "Delia Derbyshire"  |
| :london     | "Ziggy Stardust and the Spiders from Mars"     |

To define this "table" in Ruby we would type (and you should test out in
IRB!):

```irb
english_bands_by_city = {
 :liverpool =>   "The Beatles",
 :manchester =>  "The Smiths",
 :coventry =>    "Delia Derbyshire and the BBC Radiophonic Band",
 :london =>      "Ziggy Stardust and the Spiders from Mars"
}
```

You provide a name, an assignment operator and then a list of pairs, separated
by commmas, that should go in the `Hash`, wrapped in `{}`. Each pair should
have name (typically a `Symbol`), a "rocket" symbol `=>`, and a value. A value
is often a scalar value, but it could be another collection, more on that
later.

## Define `Hash` Key

Hashes are like tables that have an identifier that is a piece of data,
typically a `Symbol` or a `String`. This identifier is called a _key_

> **REMINDER** `Symbols` are like `Strings` except that they start with `:`
> and have some other interesting features from Ruby's perspective.

## Define `Hash` Value

The value that's returned from asking a `Hash` what a given _key_ points to is
known as the key's _value_.

## Demonstrate Nesting of Collection Data Structures

We want to provide a really complex example of Array and Hash working together.
Most programming texts don't share this early and it makes "nesting" sound
scary and complex. We're going to give you a short demonstration here so that
you can see why you want to have these complex data structures. The details on
how to build them, etc. will come in later lessons.

The _elements_ in an _Array_ and the _values_ in a _Hash_ can be `Hash`es or
`Array`s _themselves_. This leads to "nesting" such that you could build a
complex data structure like the following:

```ruby
english_music_by_city = {
  :manchester => [
    {
      :band_name => "The Smiths",
      :member_names => ["Morrissey", "Johnny", "Andy", "Mike"]
    },
    {
      :band_name => "Joy Division",
      :member_names => ["Peter", "Stephen", "Bernard", "Ian"]
    },
  ]
}
```
The _abstraction_ `english_bands_by_city` hides the complexity in that piece of data.

## Conclusion

This is has been a whirlwind tour of Ruby's collection data types, Hash and
Array. Individually each are data structures that can hold list- and
dictionary-like data. Amazingly, they can _hold each other_ and that means we
can make very complex data structures from them.
