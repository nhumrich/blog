---

layout: post
title: Python Gems
quote: A Few of my Favorite Things
image: /media/python3d_edit.png
video: false
comments: true
---

Python has a lot of great things to love. Whenever I think about why I like python so much, these are some of the things thats stick out to me.
These things can really speed up development time and make things easier to program. 

## Tuple Tuple Tuple

Not unique to python but still cool is the concept of a tuple. A tuple is kind of like a list, but a little easier to use. 
Lets say I wanted some type of list of objects usually because I want a pair of things. For example, I want to store an item price, and a name together.
Your first option is you could create an object, set the properties on the object, then store the object. But often objects are just too heavy for simple things.
The next option is use a list. Typically with lists, you have to create a list first, then add the objects to it.

```python
item = list()
item.append(50)
item.append('sunglasses')

print(item)  # [50, 'sunglasses']
print(item[0])  # 50
```

Thats a lot of work for what supposed to be an easy solution. Python has also a tuple. A tuple is also an iterable, so it can be looped over like a list.
Tuples can be specified in line.

```python
item = (50, 'sunglasses')

print(item)  # (50, 'sunglasses')
print(item[0])  # 50
```

Really the only difference between a tuple and a list is the `()` instead of the `[]`. The power of tuples is that you can do them in one line, with any object. 
Where tuples get really cool is with automatic packing and unpacking.
## Pack your bags!

Python has this cool little thing called "packing". This is where python automatically packs multiple objects into a Tuple. 
Python can pack, but it can also unpack, and it does this all automatically. Packing is usually used when you want to return multiple things.
Since its not really possible for languages to return multiple things (due to how low level programming and call stacks work), python 
achieves this by "packing" the objects into a tuple.

```python
def get_sunglasses():
  return 50, 'sunglasses'
```

Using this syntax, we are essentually returning multiple things. What python is actually doing is packing these two things into a single tuple.
Now the caller of the function can either use a single variable for the return value, in which case they will get a tuple, or they can 
use two variables, in which case python will automatically unpack them and assign the tuple values to the variables.

```python
# Using a single variable
item = get_sunglasses()
print(item)  # (50, 'sunglasses')

# Using multiple variables, thus causing python to unpack
value, item_name = get_sunglasses()
print(value)  # 50
print(item_name)  # 'sunglasses'
```

Unpacking also works on any type of list/interable. The only rule is that your number of variables has to either be 1, or match the number of items in the list exactly or you will get a "too many values to unpack" error message.


## Generators

## Comprendo?
