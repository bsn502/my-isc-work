NCAS Introduction to Scientific Computing

Python

cd my-isc-work/python_work

#pythagoras
b=3
c=4

a=(b**2+c**2)**0.5

a=0.5

name =  "Beth"

if name == "Fred":
	print "Hi Fred"
elif name == "Beth":
	print "Hello"
else:
	print  "Who are you?"

#  cannot add string to integer. a is a string, c is an integer

print a + str(c)

# computer will estimate floats - it has rounding errors!

float("56.7")
56.700000000000003

#while

while counter < 5:
...     print "hello", counter
...     counter += 1 #same as : counter = counter + 1

index = 0 #index from 0
>>> while index < 4:
...     print index, stuff[index]
...     index += 1 #index = index + 1
... 
0 hello
1 3
2 3.555
3 bye

len(stuff)
4

len('hello')
5

#elifs, else, ifs

x = 0
if x ==2
	print X
elif x == 1:
	print x
else:
	"horray"

#indexing and slicing

x = "Hooray"
x[0]
'H'
x[-1]
'y'
x[-2]
'a'

#what if I want "oo"? index 0 = before H, index 1 = between H and first O etc
x[1:3]
'oo'
x[1:]
'orray'
x[:]
'Horray'

# look into lists
>>> l = range(5)
>>> l
[0, 1, 2, 3, 4]
>>> dir(l)
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__delslice__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getslice__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__setslice__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'coun

#interested in append

>>> l.append("lunch")
>>> l
[0, 1, 2, 3, 4, 'lunch']
>>> l.remove("lunch")
>>> l
[0, 1, 2, 3, 4]

#sort list in place without returning
l = [4,7,2,3]
l.sort()
l
[2,3,4,7]

#variables must begin with letter or underscore. Cannot have spaces, - or +

#I will go into block whilst x = 1, I will print it and remove the  first 1

>>> x = [1, 1, 4, 5, 1 ,1]
>>> while 1 in x:
...     print x
...     x.remove(1)

[1, 1, 4, 5, 1, 1]
[1, 4, 5, 1, 1]
[4, 5, 1, 1]
[4, 5, 1]

#removes the ones until they are all gone. Keeps looping round.

#Will print the things in the list without duplicates
s = set(x)
s
[1,4,5] or just [4,5] if you've gone through the loops to remove 1s.

#you can use " " and ' ' interchangeably as long as you're consistant. 

#Lists are mutable (can modify after creation). Tuples are not.

primes   = (2,3,5,7)
print primes[0], primes[-1]
2 7

#if you just have one element you need a comma - (5,)

left, right, middle = 2, 7, 5
print right
7

def bounds(values):
	low = min(values)
	high = max(values)
	return (low, high)
print bounds([3,-5,9,4,17])
(-5, 17)
#can do the same with lists

pairs = [(1,10), (2,20), (3,30)]
for (low, high) in pairs:
	print low+high
#prints 1+10, 2+20 etc

#Tuples

#create tuple named "t" with one integer, "1"
t = (1,)
#print last value of tuple
print t[-1]

#Create tuple containing all values from 100 to 200
l = range(100, 201)
tup = tuple(l)
#Print first and last item in tuple
print tup[0], tup[-1]
100 200

#for vs enumerate functions

#for
>>> mylist = [23, "hi", 2.4e-10]
>>> for item in mylist:
...     print item, mylist.index(item)
... 
23 0
hi 1
2.4e-10 2
>>> 

#enumerate
>>> mylist = [23, "hi", 2.4e-10]
>>> for (count, item) in enumerate(mylist):
...     print count, item
... 
0 23
1 hi
2 2.4e-10

#Assigning and reassigning variables
>>> (first,middle,last) = mylist
>>> print first, middle, last
23 hi 2.4e-10
>>> (first,middle,last) = (middle,last,first)
>>> print first, middle, last
hi 2.4e-10 23
>>> 







