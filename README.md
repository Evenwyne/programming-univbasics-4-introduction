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
values like:

  * `String`s
  * `Integer`s
  * `Float`s
  * etc.

But sometimes we want to refer to a _collection_ of values by a common name.
This is very natural in conversation: we know "The Beatles" refer to four guys
from Liverpool who sang "I Wanna Hold Your Hand." "Grocery List" is something
that contains multiple small elements that we identify by "the third item on my
grocery list, or the last item on my grocery list." Ordered lists in Ruby are
called "Arrays."

<p align="center">
 <img width="300" src="https://curriculum-content.s3.amazonaws.com/programming-univbasics-4/introduction/Image_125_Scroll w-List.png" alt="Scroll"/>
</p>

Another collection type we know about from daily life are dictionaries: we use
one thing to "look up" a value. We "look up" the word "computer" in a real
dictionary and we are "pointed to" a long `String` that tells us what the word
means. Lookup tables, or dictionaries, in Ruby, are called "Hashes."

<p align="center">
 <img width="300" src="https://curriculum-content.s3.amazonaws.com/programming-univbasics-4/introduction/Image_126_Dictionary.png" alt="Dictionary"/>
</p>

Learning to store and to work with the data held in data structures will be the
focus of this module. A video on the basics of arrays and hashes is included below.
In the remainder of the lesson, we'll give you a broad, conceptual introduction to
collection data types.

## Video: Arrays and Hashes

This video provides an overview of everything we will learn and practice in
next few lessons. We will revisit each of the discussed concepts in detail, but watching
this video now will give you a good high-level view of how arrays and hashes work.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9m4SJOqxoYI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Compare Collection Data Types to Scalar Data Types

`String`s, `Integer`s, and `Float`s are scalar data types, they can be put on a
scale. A collection type holds multiple pieces of data and allows us to talk
about the collection as an _abstraction_. "The Beatles" is an _abstraction_
used to refer to the individuals John, Paul, George, and Ringo. Because
collection types can't be put on a scale, they ***are not*** called scalar data
types.

## Define `Array`

An `Array` is a collection that holds multiple pieces of data under a single
name ("Gryffindors", "Countries"). In daily life, we call them "lists."

**The Beatles**

|Index|Data|
|-----|----|
| `0`   | `"John Lennon"`     |
| `1`   | `"Paul McCartney"`  |
| `2`   | `"Ringo Starr"`     |
| `3`   | `"George Harrison"` |

or

**Groceries**

|Index|Data|
|-----|----|
| `0`   | "Parsnips"`           |
| `1`   | "English Toffee"`     |
| `2`   | "Milk"`               |
| `3`   | "Sprouted Rye Bread"` |

The individuals _elements_ that make up this collection (or list) name are
identified by an _index_.

<p align="center">
  <img width="500" src="https://curriculum-content.s3.amazonaws.com/programming-univbasics-4/introduction/Image_127_Beatles.png" alt="Beatles"/>
</p>

It might seem strange that we start our list at `0` instead of `1`. Programmers
like `0` and most programming languages start their index at `0`. Otherwise,
it's pretty much a list like you've been making most of your life.

To define this "list" in Ruby we would type (and you should test out in
IRB!):

```ruby
the_beatles = [ "John Lennon", "Paul McCartney", "Ringo Starr", "George Harrison"]
```

You provide a name (`the_beatles`), an assignment operator (`=`)and then a list of data, separated
by commas, that should go in the `Array`, wrapped in `[]`. Each bit of
information is often a scalar value, but it could also be another collection
(more on that later).

## Define `Array` Element / Member

The individual pieces of data inside an `Array` are called _elements_. Some
people also call the _elements_ the _members_. In a collection of
`the_beatles`, the `String` `"George Harrison"` is an _element_.

## Define `Array` Index

`Array`s provide a number that identifies each _element_ called an _index_. The
index for the _element_ `"Ringo Starr"` above is `2`.

We'll cover adding, removing, retrieving, and deleting _elements_ via their
_index_ in another lesson.

## Define `Hash`

Another way of thinking about `Array`s is that they are like tables that have
an identifier that is an `Integer`. If we let the identifier be a `String` or a
`Symbol` _instead_ of an `Integer`, then we'd basically be describing a `Hash`.


<p align="center">
 <img width="300" src="https://curriculum-content.s3.amazonaws.com/programming-univbasics-4/introduction/Image_130_HashDefinition.png" alt="Hash Definition"/>
</p>

What if we wanted to take our list of the Beatles and describe each member not
by some `Integer` _index_, but rather by the instrument they played in the band? As a
table this might look like:

![Array to Hash conversion graphic](https://curriculum-content.s3.amazonaws.com/programming-univbasics-4/introduction/Image_129_Array2HashConversion.png)

A `Hash` is a collection data type that holds multiple pieces of data under a
collected name whose members can be read and updated by using a _key_ instead
of an _index_. In daily conversation we use _keys_ to retrieve _values_
all the time: "Who was the guy who played **drums** in **The Beatles**?"

We can think of `Hash`es like a table that looks like this:

|Key|Value|
|-----|----|
| `:liverpool`  | `"The Beatles"`     |
| `:manchester` | `"The Smiths"`  |
| `:coventry`   | `"Delia Derbyshire and the BBC Radiophonic Band"`  |
| `:london`     | `"Ziggy Stardust and the Spiders from Mars"`     |

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

You provide a name (`english_music_by_city`), an assignment operator (`=`) and
then a list of pairs, separated by commas, that should go in the `Hash`,
wrapped in `{}`. Each pair should have a name (typically a `Symbol`), a
"rocket" symbol (`=>`), and a value. A value is often a scalar value, but it
could be another collection, more on that later.

## Define `Hash` Key

`Hash`es are like tables that have a name that is a piece of data, typically a
`Symbol` or a `String`. This identifier is called a _key_.

> **REMINDER** `Symbols` are like `Strings` except that they start with `:`
> and have some other interesting features from Ruby's perspective. Most
> Rubyists prefer to use `Symbol`s for `Hash` keys.

## Define `Hash` Value

The value that's returned from asking a `Hash` what a given _key_ points to is
known as the key's _value_.

We'll cover adding, removing, retrieving, and deleting _elements_ via their
_key_ in another lesson.

## Demonstrate Nesting of Collection Data Structures

Now that you know about `Array`s (grocery lists, band members, todo lists) and
`Hash`es (abbreviation to full name lookup, a stock symbol to trading value
lookup, instrument to band member name lookup) you might be a bit unimpressed.
"Surely the world's data needs are more complex than simple lists and lookup
tables," you might exclaim.

You'd be right, but the amazing thing about collections is that they can
contain _other_ collections as part of a process called _nesting_. Can you
imagine an `Array` of `Hash`es? Or a `Hash` of `Arrays` of `Hash`es of
`Array`s? You can cover a staggeringly huge model of data with nesting of these
two data types.

We want to provide a really complex example of `Array` and `Hash` working together.
Most programming texts don't share this concept this early and it makes "nesting" sound
scary and complex. We're going to give you a short demonstration here so that
you can see why you want to have these complex data structures. The details on
how to build them etc. will come in later lessons.

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

As a peek ahead, we can use the lookup operator (`[]`) to "dig into" this nested collection
and get interesting information out:

```ruby
english_music_by_city[:manchester][0][:band_name] #=> "The Smiths"
english_music_by_city[:manchester][0][:member_names] #=> ["Morrissey", "Johnny", "Andy", "Mike"]

puts "There were #{english_music_by_city[:manchester][0][:member_names].length} members in #{english_music_by_city[:manchester][0][:band_name]}"
#=> "There were 4 members in The Smiths"
```

## Conclusion

This is has been a broad tour of Ruby's collection data types, `Hash` and
Array.  Individually they are data structures that can hold list- and
dictionary-like data. Amazingly, they can even _hold each other_ &mdash; and
that means we can make very complex data structures from them! We'll practice
with these types in the following lessons!
