NCAS Introduction to Scientific Computing

Python

cd my-isc-work/python_work

git add README.txt
git commit -m"pythonreadme"
git push
if you change something on remote  repository, do git pull

git commit -a -m"pythonreadme"
git push

Linux remembers history. Press ctrl+r searches all commands you've ever run

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
>>> type(tup)
type 'tuple'

#Input and output
with open('haiku.txt', 'r') as reader:
	date = reader.read()

#open is a built in function - allows to open file object. 'r' if we want to read. 'w' if you want to write to file. Open file handle is known as 'reader'. Reader is a variable representing the file object connected to 'haiku.tct'.Use reader object to read from it. () = read entire content of file. Reads all file into single string. Date then becomes a string. 'with' statement closes the file as soon as you leave the indentation.

print len(data) #prints characters/bytes

#only with v v large data
with open('haiku.txt', 'r') as reader:
	data = reader.read(64) #read (at most) 64 characters/bytes
	while data!= ": #whilst data is not an empty string, we will go into block and process it
		print len(data)
		data = reader.read(64) #call reader again. Overide previous data variable and read the next 64 bytes
print len(data) # should be 0 since gone through loop and finished.
64
64
64
37 #(at most)
0 #data is empty ot exits the loop

#long winded but better
with open ('haiku.txt', 'r') as reader:
	line = reader.readline()
	total = 0 #no of characters
	count = 0 #lines
	while line != "": #as long as there is something in line...
	count += 1
	total += len(line)
	line = reader.readline()
print 'average', float(total) / float(count) #convert into float so we get decimals

average 19.53333333

#more convenient
with open('haiku.txt', 'r') as reader:
	contents = reader.readline() #read all lines in file as list of strings
	total = 0
	count = 0
	for line in reader: #read all lines in one by one inside loop
		count += 1
		total += len(line)
print 'average', float(total) / float(count)

average 19.53333333

#writing files using write or writelines
with open('temp.txt', 'w') as writer:
	writer.write('elements') #write a single string
	writer.writelines(['He', 'Ne', 'Ar', 'Kr']) #write each list as string in line

elementsHeNeArKr #writes with no white space

#writing files using write or writelines
with open('temp.txt', 'w') as writer:
	writer.write('elements\n') 
	writer.writelines(['He\n', 'Ne\n', 'Ar\n', 'Kr\n'] #\t would put tab in

elements
He
Ne
Ar
Kr #inserted white space!

#Read contents of csv file and display each line
>>> with open ('weather.csv', 'r') as reader:
...     data = reader.read()
... 
>>> print data
Date,Time,Temp,Rainfall
2014-01-01,00:00,2.34,4.45
2014-01-01,12:00,6.70,8.34
2014-01-02,00:00,-1.34,10.25

#Read the file line by line
with open("weather.csv") as reader:
...     line = reader.readline()
...     while line:
...             print line
...             line = reader.readline()
... 
Date,Time,Temp,Rainfall

2014-01-01,00:00,2.34,4.45

2014-01-01,12:00,6.70,8.34

2014-01-02,00:00,-1.34,10.25

#Reading the file line by line
>>> with open("weather.csv") as reader:
...     line = reader.readline()
...     while line:
...             print line
...             line = reader.readline()
... 
Date,Time,Temp,Rainfall

2014-01-01,00:00,2.34,4.45

2014-01-01,12:00,6.70,8.34

2014-01-02,00:00,-1.34,10.25
>>> print "It's over"
It's over

#Use a "for" loop to grab just rainfall values
>>> with open("weather.csv") as reader:
...     header = reader.readline()
...     rain = []
...     for line in reader.readlines():
...             r=line.strip().split(",")[-1] #line.strip() strips any white space. Then you split the strip by commas. The get last item in list.
...             r=float(r) #could combine e.g. float(line.strip().split(",")[-1])
...             rain.append(r)
... 
>>> print rain
[4.4500000000000002, 8.3399999999999999, 10.25]

#Reading and writing binary data (ADVANCED)
>>> import struct
>>> bin_data = struct.pack("bbbb", 123, 12, 45, 34)
>>> with open("mybinary.dat", "wb") as bwriter:
...     bwriter.write(bin_data)
... 
>>> with open("mybinary.dat", "rb") as breader:
...     bin_data2 = breader.read()
... 
>>> data = struct.unpack("bbbb", bin_data2)
>>> print data
(123, 12, 45, 34)

#strings - sequences of characters

name = 'Darwin' #string of length 6
for c in name: #character variable
	print c
D
a
r
w
i
n

print '100' < '9'
TRUE #true because only looks at first character and 1 < 9

#strings are immutable - you cannot change them! Immutable to improve performance
>>> original = 'Charles'
>>> name = original
>>> name += 'Darwin'
>>> print name
'CharlesDarwin'

{ brackets are formatters 
'{0}, {1}, {2}'.format('a', 'b' 'c') #insert arguments a, b and c into string template 0, 1, 2.

#.2f formats to 2 decimal places
# \n represent new line character
print 'There isn\'t time\nto do it right.'
There isn't time
to do it right.

>>> Most mathematicians write a\\b instead of a%b
Most mathematicians write a\b instead of a%b

name = 'newTON'
>>> print name.capitalize(), name.upper(), name.lower(), name
Newton NEWTON newton newTON

>>> DNA = 'ACGGTGGTCAC'
>>> print dna.count('g'), dna.count('x'
4 0
>>> print dna.find('t'), dna.find('t',5) #start looking for t at 5th point
4 7
>>> dna.find('x')
-1 #if something not there returns -1 but python thinks -1  is true! python issue
>>>print dna.replace('T', 'X'), dna
ACGGXGGXCAC

#look into "regular expressions" in own time

#loop through string as a sequence
s  = "I love to write python"
>>> for i in s:
...     print i
... 
I
 
l
o
v
e
 
t
o
 
w
r
i
t
e
 
p
y
t
h
o
n

>>> print s[4]
v
>>> print s[-1]
n
>>> print len(s) #character length of s
22
>>> print s[0]
I
>>> print s[0][0]
I
>>> print s[0][0][0]
I

#split a string to loop through its words (rather than characters)
>>> s = "I love to write python"
>>> split_s = s.split()
>>> print split_s
['I', 'love', 'to', 'write', 'python']
for word in split_s:
...     if word.find("i") > -1:
...             print "I found 'i' in: '{0}'".format(word)
... 
I found 'i' in: 'write'

#exploring useful aspects of strings
>>> something = "Completely Different"
>>> print dir(something)
['__add__', '__class__', '__contains__', '__delattr__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__getslice__', '__gt__', '__hash__', '__init__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '_formatter_field_name_split', '_formatter_parser', 'capitalize', 'center', 'count', 'decode', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'index', 'isalnum', 'isalpha', 'isdigit', 'islower', 'isspace', 'istitle', 'isupper', 'join', 'ljust',
>>> something.count("t")
2
>>> something.find("plete")
3
>>> something.split("e")
['Compl', 't', 'ly Diff', 'r', 'nt']
>>> thing2 = something.replace("Different", "Silly")
>>> print thing2
Completely Silly

#strings cannot be changed!
>>> something[0] = "B"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment

#Aliasing = any mutable object can be subject to aliasing

a = [[0,1,2],[0,1,2]]
b  = a[1]
print b
[0,1,2]
#if we change b to [0,hello,2] then we also change a to [[0,1,2],[0,hello,2]]
#this is efficient for big datasets. If one thing in b is wrong we can change it and also change a to go along with it.

#Can keep original versions by using the copy.deepcopy function. This creates a new copy from memory that you can change without altering the original dataset.

#functions

#Creating a simple function
>>> def double_it(number):
...     return 2 * number
... 
>>> double_it (2)
4
>>> double_it (3.5)
7.0
>>> double_it ("hello")
'hellohello'

#Calculate length of hypotenuse of right angled triange
>>> def calc_hypo(a, b):
...     hypo = (a**2 + b**2)**0.5
...     return hypo
... 
>>> print calc_hypo(3, 4)
5.0

#Improve function by adding checks to the code
>>> def calc_hypo(a, b):
...     if type(a) not in (int, float) or type(b) not in (int, float):
...             print "Bad argument"
...             return False
...     if a <= 0 or b <= 0:
...             print "Bad argument"
...             return False
...     hypo = (a**2 + b**2)**0.5
...     return hypo
... 
>>> calc_hypo(0, -2)
Bad argument
False
>>> calc_hypo("hi", "bye")
Bad argument
False
>>> calc_hypo(3, 4)
5.0

#in linux
#make python library called "dancing"
[user01@unst26 python_work]$ mkdir dancing
[user01@unst26 python_work]$ python -c "import dancing"
Traceback (most recent call last):
  File "<string>", line 1, in <module>
ImportError: No module named dancing
[user01@unst26 python_work]$ touch dancing/__init__.py #"touch" creates a file if it's not there
[user01@unst26 python_work]$ python -c "import dancing"

#create dance.py module inside library
[user01@unst26 exercises]$ cp example_code/dance.py dancing/ #dancing/ at the end is telling it where you want it to be copied to
[user01@unst26 ~]$ cd my-isc-work/python_work
[user01@unst26 python_work]$ python -c "import dancing.dance"
[user01@unst26 python_work]$ python -c "from dancing.dance import boogie"

#4 line script allowing users to interact with library
NOT SURE HOW TO CREATE SCRIPT

#Sets - sets are mutable - it can be modified - NB ordering in sets is random
a.clear() # removes all items in set a
letters = set('qwertyuiop')
len(a) - gives number of elements
a ^ b - in set a OR set b

>>> a = set([0, 1, 2, 3, 4, 5])
>>> b = set([2,4,6,8])
>>> print a.union(b)
set([0, 1, 2, 3, 4, 5, 6, 8])
>>> print a.intersection(b)
set([2, 4])

#python2.7

a = [1,2,3] list, can be changed
t  = (1,2,3) tuple cannot be changed
tup = tuple(a) converts a into a tuple called tup
a = x,y,z
x = 1, y = 2, z = 3

for (count, item)  in enumerate(a):
		print count, item
0 1
1 2
2 3

for i in enumerate(a):
	print i
(0, 1)
(1, 2)
(2, 3)

for (count, item) in enumerate(a):
	print count, item
0 1
1 2
2 3

with open('data.csv', 'r') as freader:
	data = freader.read() #read returns everything you've read in in a single string
23, 45, 78...

with open('data.csv', 'r') as freader:
	for line in freader.readlines():
	print line
25, 45, 78

1, 77, 2.. etc #prints each line

with open('data.csv', 'r') as freader:
	for line in freader: #don't need to put readlines (shortcut)
		print line.strip()
25, 45, 78
1, 77, 2..

with open('output.csv', 'w') as freader:
	fwriter.write("Hello\nWorld\n")
	print line
$more output.csv
Hello
World

s = "Hi"
s(dir) - lists all the things you can do with string, s
s.upper()
"HI"
s.title()
'Hi'
s.startswith("H")
True

s = "aab"
s.count("a)
2 # there are two as in string, s

s.find("c")
-1 #there are no cs in string, s

if s.find("c"):
	print "FOUND"
FOUND
if -1:
	print "TRUE"
TRUE
if s.find("c) != -1: #if s does not contain -1
	pring "FOUND"

if s.find("c) > 0: #if s does not contain -1
	pring "FOUND"

b= copy.deepcopy(a) #creates a copy of original

def hello(person):
	print "Hello {}".format(person)

for person in ["Fred", "Harry", "Hermione"]:
	hello(person)

$ cd tmp
$ ls
$ mkdir mylib
$ touch mylib/__init__.py
python2.7
import mylib
vi mylib/myfuncs.py #vi - create script?

#Dictionaries - An unordered collection of key/value pairs
#Keys are immutable e.g. a tuple could be a dictionary key but not a list
#sorted in no particular order

#Create dictionary by putting key:value pairs in {}
>>> birthdays = {'Newton' : 1642, 'Darwin' : 1809}

#Retrieve values by putting key in []
>>> print birthdays['Newton']
1642

#Changing values in dictionary
>>> birthdays['Turing'] = 1612 #birthday not correct
>>> print birthdays
{'Turing': 1612, 'Newton': 1643, 'Darwin': 1809}
>>> birthdays['Turing'] = 1912
>>> print birthdays
{'Turing': 1912, 'Newton': 1643, 'Darwin': 1809}

#Not in dictionary
>>> birthdays['Nightingale']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Nightingale'

#Test if key in present using in
>>> 'Nightingale' in birthdays
False
>>> 'Darwin' in birthdays
True

#Loop over dictionary using for NOT WORKING
for name in birthdays:
...     print name, birthdays[name]
... 
Turing 1912
Newton 1642
Darwin 1809

#Useful methods on dictionaries
>>> person  = {"name" : "Sarah", "height" : 2}
>>> person.keys()
['name', 'height']
>>> person.values()
['Sarah', 2]
>>> person.items()
[('name', 'Sarah'), ('height', 2)]
>>> person.setdefault ('profession', 'astrophysicist')
'astrophysicist'
>>> person
{'profession': 'astrophysicist', 'name': 'Sarah', 'height': 2}

>>> band = ["mel", "geri", "victoria", "mel", "emma"]
>>> counts = {} #create empty dictionary
>>> for name in band:
...     if name not in counts:
...             counts[name] = 1
...     else:
...             counts[name] += 1
...
>>> for name in counts:
...     print name, counts[name]

#Useful characters in dictionaries
>>> d = {"maggie" : "uk", "ronnie": "usa"}
>>> dir(d)
['__class__', '__cmp__', '__contains__', '__delattr__', '__delitem__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'clear', 'copy', 'fromkeys', 'get', 'has_key', 'items', 'iteritems', 'iterkeys', 'itervalues', 'keys', 'pop', 'popitem', 'setdefault', 'update', 'values', 'viewitems', 'viewkeys', 'viewvalues']
>>> print d.items()
[('maggie', 'uk'), ('ronnie', 'usa')]
>>> print d.keys()
['maggie', 'ronnie']
>>> print d.values()
['uk', 'usa']
>>> d.get("maggie", "nowhere") #if you have a value for location of maggie give it, if not give nowhere
'uk'
>>> d.get("ringo", "nowhere")
'nowhere'
>>> res = d.setdefault("mikhail", "ussr")
>>> print res d["mikhail"]
>>> print res, d["mikhail"]
ussr ussr
>>> print d
{'maggie': 'uk', 'mikhail': 'ussr', 'ronnie': 'usa'}

#errors

#syntax errors - python cannot read what you've typed
>>> while true print 'Hello world'
ERROR
>>> while true, print 'Hello  world' #better
#Exceptions are not unconditionally fatal.
#ZeroDivisionError, NameError, TypeError, KeyError.

try:
	result - runMyClimateModel
except:
	you can tell it to email you or print a message to raise a problem if model is bad

if validate(input) == False:
	raise Exception("Bad input provided")
#Programme will stop here unless this exception is caught
	else:
		print "great input"

def readIntFromFile(fname):
	"returns an integer from a file."
with open(fname) as f:
	my_int = int(f.read(10)) 
#read stuff out of file as return as integer

for f in ("a.txt", "b.txt", "c.txt"):
	try:
		print readIntFromFile(f)
	exceptIOError:
		print "There is nothing in the file..."
	except ValueErrorL:
		print "The contents is not an integer..."
	except Exception, err:
		print "Really unexpected error"...

#you can thus capture and handle errors!

#Logging and debugging
#Python has the "logging" module which allows you to log in may useful ways: to the terminal; to files; to custon-handlers (email); to system log files

#pythondebugger - set break points in the code where you can go into code and interrogate.  Fix problems.
>>> import pdb #pythons debugger
>>> pdb.set_trace() #to add break point
(pdb) x #let's look at x

#Object orientated programming (OOP)
ADVANCED...

--------------------------------------------------------------------------

#NumPy

#an array is like a list except: elements are of same type, multi-dimensional arrays are more clearly supported, array operations are supported
#NumPy is written in C so processing of large arrays is faster than lists
#import package numpy. Often imported as an alias:

import numpy as np (np.________)

>>>import numpy as np
>>> a = np.arrray([[2,3,-5], [21,-2,1]]
	dtype = np.int32)

>>>np.float64 #Double precision float
>>>np.floar32 #Single precision float
>>>np.int8 #Byte
>>>np.int64 #Long integer (64 bit)

>>>a = np.zeros((3,2), dtype=np.float64) #creates 3 by 2 array filled with zeros
>>>a = np.arange(10) #gives one dimensional array will defalt to integers
#The first element of 1-D array   a is  a[0], the second is a[1], a[-1] is last etc
#ranges can be expressed by colon a[4:8] #counts in between elements so ends just before 9th element
#multi-dimensional - [row, col]. Indexing between different dimensions is separated by commas.

#Create a numpy array from a list
>>> a1 = np.array(x, np.int32)
>>> print a1
[ 1  2  3  4  5  6  7  8  9 10]

>>> a2 = np.array(x, np.float32)
>>> print a2
[  1.   2.   3.   4.   5.   6.   7.   8.   9.  10.]

>>> print a1.dtype
int32
>>> print a2.dtype
float32

#Create arrays in different ways
>>> arr = np.zeros((2, 3, 4))
>>> print arr
[[[ 0.  0.  0.  0.]
  [ 0.  0.  0.  0.]
  [ 0.  0.  0.  0.]]

 [[ 0.  0.  0.  0.]
  [ 0.  0.  0.  0.]
  [ 0.  0.  0.  0.]]]
>>> arr = np.ones((2, 3, 4))
>>> print arr
[[[ 1.  1.  1.  1.]
  [ 1.  1.  1.  1.]
  [ 1.  1.  1.  1.]]

 [[ 1.  1.  1.  1.]
  [ 1.  1.  1.  1.]
  [ 1.  1.  1.  1.]]]
>>> arr = np.arange(1000) #points between so goes up to 999
>>> print arr
[  0   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17
  18  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34  35
  36  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51  52...999]

#Indexing and slicing arrays
>>> a = np.array([2, 3.2, 5.5, -6.4, -2.2, 2.4])
>>> print a[1]
3.2
>>> print a[1:4]
[ 3.2  5.5 -6.4]
>>> a = np.array([[2, 3.2, 5.5, -6.4, -2.2, 2.4],[1, 22, 4, 0.1, 5.3, -9],[ 3, 1, 2.1, 21, 1.1, -2]])
>>> print a[:, 3]
[ -6.4   0.1  21. ] #21 has a point following it because if one is a float, they all have to be. Prints everything in the first [] ([] number 0) after point 3
>>> print a[1:4, 0:4]
[[  1.   22.    4.    0.1] 
 [  3.    1.    2.1  21. ]] #print []s 1-4 which is the second one to after the end (4th one doesn't exist). Within each give point 0 to 4 (first 4 values)
>>> print a[1:, 2]
[ 4.   2.1] #prints from the second [] ([] number 1) and also the thrid [] ([] number 3). Prints the value after the second counter in each.

#Interrogating arrays

np.shape(a) #returns tuple
np.ndim(a) #rank / no. of dimensions
np.size(a) #number of elements
np.max(a) #or ##np.min(a) #find the maximum and minimum of the array

#manipulating the array - all return a new array
np.reshape (a, (2,3)) #reshapes the array
np.transpose(a) #transpose the array
np.ravel(a) #flatten to a 1-D array. May be useful when  dealing with model data
np.concatenate((a,b)) #concatenate array. Give a tuple containing a no. of numpy arrays. concats on first dimension or axis.
np.repeat(a, 3) #repeat array elements

#Arrays as objects
a.shape = np.shape(a) # = literal meaning of =
a.max = np.max(a) # = literal meaning of =
a.repeat(3) = np.repeat(a,3) # = literal meaning of =
b = a.astype(np.int32) #convert data type
np.average(a) #use this since a.average doesn't exist

#Interogating the array to find out its characteristics
>>> import numpy as np
>>> arr = np.array([range(4), range(10, 14)])
>>> print arr.shape
(2, 4)
>>> print arr.size
8
>>> print arr.max()
13
>>> print arr.min()
0

#Generate new ways of modifying the array
>>> import numpy as np
>>> arr = np.array([range(4), range(10, 14)])
>>> print arr.shape
(2, 4)
>>> print arr.size
8
>>> print arr.max()
13
>>> print arr.min()
0
>>> print np.reshape(arr, (2,2,2))
[[[ 0  1]
  [ 2  3]]

 [[10 11]
  [12 13]]]
>>> print np.transpose(arr)
[[ 0 10]
 [ 1 11]
 [ 2 12]
 [ 3 13]]
>>> print np.ravel(arr)
[ 0  1  2  3 10 11 12 13]
>>> print arr.astype(np.float64)
[[  0.   1.   2.   3.]
 [ 10.  11.  12.  13.]]

#Multiply two arrays together, element by element
import numpy as np
a = np.array([[2, 3.2, 5.5, -6.4], [3, 1, 2.1, 21]])
b = np.array([[4, 1.2, -4, 9.1], [6, 21, 1.5, -27]])
shape_a = a.shape
product_ab = np.zeros(shape_a, dtype=np.float32)

for i in xrange(shape_a[0]):
	for j in xrange (shape_a[1]):
etc

#xrange loops are very slow so don't do it this way

product_ab = a * b #best way to do it
c = a + c
#this works faster since looping happens in compiled code inside library that is optimised rather than inside your programme.

#old way
for i in xrange(shape_a[0]):
	for j in xrange (shape_a[1]):
	if (a[i,j] > 5) and (a[i,j] < 10):
			answer[i,j] = a[i,j] * 2
		else:
			pass #do nothing
#new way
answer = a > 5
answer = np.greater(a, 5)
#new way boolean operators
np.logical_not(a > 3)
np.logical_and(a > 3,a < 5)

#with where function
condition = np.logical_and(a > 3,a < 5)
answer = np.where(condition, a * 2, 0)
#all places where true, end up with a*2, all places where false get 0

#Mathematical and statistical functions:
np.interp
np.sin
np.exp
np.histogram
np.hamming
np.fft

#other functions
dir(np)
help(np)
help(np.x) where x is the name of a function
dir(a) and help(a) where a is the name of an array

#Performing some array calculations
>>> import numpy as np
>>> a = np.array([range(4), range(10, 14)])
>>> b = np.array([2, -1, 1, 0])
>>> print a * b
[[  0  -1   2   0]
 [ 20 -11  12   0]]
>>> b1 = b * 100
>>> b2 =  b * 100.0
>>> print b1, b2
[ 200 -100  100    0] [ 200. -100.  100.    0.]
>>> print b1 == b2
[ True  True  True  True]
>>> print b1.dtype, b2.dtype
int64 float64

#Look at array comparisons
>>> arr = np.arange(10)
>>> print arr < 3
[ True  True  True False False False False False False False]
>>> print np.less(arr, 3)
[ True  True  True False False False False False False False]
>>> condition = np.logical_or(arr < 3, arr > 8)
>>> new_arr = np.where(condition, arr * 5, arr * -5)
>>> print new_arr
[  0   5  10 -15 -20 -25 -30 -35 -40  45]

#Implement a mathematical function that works on arrays
>>> def calcMagnitude(u, v, minmag = 0.1):
...     mag = ((u**2) + (v**2))**0.5
...     output = np.where(mag > minmag, mag, minmag)
...     return output
... 
>>> u = np.array([[4, 5, 6], [2, 3, 4]])
>>> v = np.array([[2, 2, 2], [1, 1, 1]])
>>> print calcMagnitude(u, v)

[[ 4.47213595  5.38516481  6.32455532]
 [ 2.23606798  3.16227766  4.12310563]]
>>> u = np.array([[4, 5, 0.01], [2, 3, 4]])
>>> v = np.array([[2, 2, 0.03], [1, 1, 1]])
>>> print calcMagnitude(u, v)
[[ 4.47213595  5.38516481  0.1       ]
 [ 2.23606798  3.16227766  4.12310563]]

#testing if fucntion works using first value in u and v
>>> x = ((4**2)+(2**2))**0.5
>>> x
4.47213595499958

#boolean is a data type that is either true or false

#Handling missing values (using masked arrays)
#A masked array includes and mask of bad values that travels with the array
#Bad elements are treated as if they don't exist.
(masked arrays - numpy.ma)

import numpy as np
import numpy.ma as MA

a = MA.masked array(data = [1, 2, 3], mask = [True, True, False])
etc

#Advantage - you can do ordinary operations without having to worry  about bad values as these are automatically masked.

#fill values
>>>print a.filled()
array([999999, 999999, 3])
MA.masked_array(data = ___, mask = ___, fill_value = 1e30) #fill value must be outside data range so it is obviously not a valid data number.

#Create a masked array and explore it
>>> import numpy.ma as MA
>>> marr = MA.masked_array(range(10), fill_value = -999)
>>> print marr, marr.fill_value
[0 1 2 3 4 5 6 7 8 9] -999
>>> marr[2] = MA.masked
>>> print marr
[0 1 -- 3 4 5 6 7 8 9]
>>> print marr.mask
[False False  True False False False False False False False]
>>> narr = MA.masked_where(marr > 6, marr)
>>> print narr
[0 1 -- 3 4 5 6 -- -- --]
>>> x = MA.filled(narr)
>>> print x
[   0    1 -999    3    4    5    6 -999 -999 -999]
>>> print type(x)
<type 'numpy.ndarray'>

#Create mask smaller than overall array
>>> m1 = MA.masked_array(range(1, 9))
>>> print m1
[1 2 3 4 5 6 7 8]
>>> m2 = m1.reshape(2,4)
>>> print m2
[[1 2 3 4]
 [5 6 7 8]]
>>> m3 = MA.masked_greater(m2, 6)
>>> print m3
[[1 2 3 4]
 [5 6 -- --]]
>>> res = m3 - np.ones((2,4))
>>> print res
[[0.0 1.0 2.0 3.0]
 [4.0 5.0 -- --]]
>>> print type(res)
<class 'numpy.ma.core.MaskedArray'>
>>> m4 =  m3 * 100
>>> print m4
[[100 200 300 400]
 [500 600 -- --]]

-----------------------------------------------------------------------
#Matplotlib - 2D plotting library produces publication quality figures
#Matlab-like interface
#open source, excellent tool

import matplotlib.pyplot as plt

plt.plot([1,2,3,4])
plt.show()
plt.pause(1) #show plot but refocus
plt.clf() #clears figure
plt.plot([1, 10, 3, 4, 9]) #plot something different

times = [0, 0.25, 0.5, 0.75]
plt.plot(times, [0, 0.5, 1], 'g--',label = "some data", times, [1,2,3,4], 'r' label = "some more data"
plt.title('Concentration of...)
plt.ylabel('Concentration...)
plt.xlabel('Time (s)')
plt.legend()
plt.show()

plt.savefig("myplot.png")

plt.figure()
plt.plot(range(5))
plt.figure(figsize = (10, 10)) #size in inches
plt.plot(range(100))
plt.show() #shows both figures

#Create plot
>>> import matplotlib.pyplot as plt
>>> plt.plot(range(10))
[<matplotlib.lines.Line2D object at 0x3163710>]
>>> plt.show()

#$CO_2 - subscripts the 2

#2
>>> import matplotlib.pyplot as plt
>>> plt.plot(range(10))
[<matplotlib.lines.Line2D object at 0x3082790>]
>>> plt.show()
>>> times = range(7)
>>> co2 = [250, 265, 272, 260, 300, 320, 289]
>>> plt.plot(times, co2)
[<matplotlib.lines.Line2D object at 0x36fe3d0>]
>>> plt.plot(times, co2, 'b--')
[<matplotlib.lines.Line2D object at 0x34c2510>]
>>> plt.title("Concentration of $CO_2 versus time")
<matplotlib.text.Text object at 0x36ebc90>
>>> plt.ylabel("$[CO_2]")
<matplotlib.text.Text object at 0x34d3390>
>>> plt.xlabel("Time(decade)")
<matplotlib.text.Text object at 0x34c6f50>
>>> plt.show()

#3
>>> times = range(7)
>>> co2 = [250, 265, 272, 260, 300, 320, 389]
>>> temp = [14.1, 15.5, 16.3, 18.1, 17.3, 19.1, 20.2]
>>> plt.plot(times, co2, 'b--', times, temp, 'r*-')
[<matplotlib.lines.Line2D object at 0x3ac2790>, <matplotlib.lines.Line2D object at 0x3ac2950>]
>>> plt.show()
plt.savefig("co2_temp.pdf")
>>> plt.savefig("co2_temp.pdf")

#histograms
import numpy as np

#Multiple axes and multiple graphs

#Reuse previous example with different axes
>>> import matplotlib.pyplot as plt
>>> fig, ax1 = plt.subplots()
>>> times = range(7)
>>> co2 = [250, 265, 272, 260, 300, 320, 389]
>>> ax1.plot(times, co2, 'b--')
[<matplotlib.lines.Line2D object at 0x2b568d0>]
>>> ax1.set_ylabel("$CO_2")
<matplotlib.text.Text object at 0x334b190>
>>> ax2 = ax1.twinx()
>>> temp = [14.1, 15.5, 16.3, 18.1, 17.3, 19.1, 20.2]
>>> ax2.plot(times, temp, "r*--")
[<matplotlib.lines.Line2D object at 0x379d9d0>]
>>> ax2.set_ylabel("Temp / degC")
<matplotlib.text.Text object at 0x377f690>
>>> plt.show()

#Draw three graphs side by side on a single page
>>> plt.subplot(1,3,1)
<matplotlib.axes._subplots.AxesSubplot object at 0x37836d0>
>>> x = range(0,10,1)
>>> plt.plot(x)
[<matplotlib.lines.Line2D object at 0x39237d0>]
>>> plt.subplot(1,3,2)
<matplotlib.axes._subplots.AxesSubplot object at 0x3923990>
>>> y=range(10,0,-1)
>>> plt.plot(y)
[<matplotlib.lines.Line2D object at 0x3b14750>]
>>> plt.subplot(1,3,3)
<matplotlib.axes._subplots.AxesSubplot object at 0x3b14910>
>>> z = [4]*10
>>> plt.plot(z)
[<matplotlib.lines.Line2D object at 0x3c68890>]
>>> plt.show()

-------------------------------------------------------

#add/take out symbols acsii and unicode
unix2dos
dos2unix

#encoding with .csv or NASA Ames (.na) files. csv files more portable / universal since you do not need excel software to read them.

#metadata - providing the  columns with names of variables. Needs to be clear what was measured e.g. degrees - degrees from north???

datetime.utcnow().isoformat() #returns the current UTC in ISO format

#Temperature probe
>>> #!usr/bin/python2.7
... import serial
>>> ser = serial.Serial(
...     port = '/dev/ttyUSB0',
...     baudrate = 9600,
...     bytesize = serial.EIGHTBITS,
...     parity = serial.PARITY_NONE,
...     stopbits = serial.STOPBITS_ONE)
>>> print ser.read(size=8)
+023.7C

#
>>> from datetime import datetime
>>> print datetime.utcnow().isoformat(), ser.read(size=8)
2017-11-17T12:12:13.003630 +026.3C
>>> datastring = ser.read(size=8)
>>> print datetime.utcnow().isoformat(), ser.read(size=8)
2017-11-17T12:14:28.382761 +029.4C

TEMPERATURE PROBE EXERCISE

#!/usr/bin/python2.7
import serial
ser = serial.Serial(
	port='/dev/ttyUSB0',
	baudrate=9600,
	bytesize=serial.EIGHTBITS,
	parity=serial.PARITY_NONE,
	stopbits=serial.STOPBITS_ONE)

print ser.read(size=8) #get +022.9C

from datetime import datetime
print datetime.utcnow().isoformat(), ser.read(size=8)

datastring=ser.read(size=8)
print datetime.utcnow().isoformat(), datastring
#since you only get data once every 10 seconds,
time can be recorded up to 10 seconds before the actual reading

while ser.isOpen():
	datastring=ser.read(size=8)
	print datetime.utcnow().isoformat(), datastring

import io
sio = io.TextIOWrapper(io.BufferedRWPair(ser, ser, 1), encoding='ascii', newline='\r')
while ser.isOpen():
	datastring=sio.readline()
	print datetime.utcnow().isoformat(), datastring

#!/usr/bin/python
from datetime import datetime
import serial, io

outfile='/tmp/serial-temperature.tsv'

ser=serial.Serial(
	port='/dev/ttyUSB0',
	baudrate=9600)

sio=io.TextIOWrapper(
	io.BufferedRWPair(ser, ser, 1),
	encoding='ascii', newline='\r')

with open(outfile,'a') as f: #append to existing files
	while ser.isOpen():
		datastring=sio.readline() #\t is tab, \n is line separator
		f.write(datetime.utcnow().isoformat() + '\t' + datastring + '\n')
		f.flush() #force system to write to disk

ser.close()

-----------------------------------------------------------------------------------------------------

#NetCDF

#NetCDF already installed on anaconda.

#Reading NetCDF files on python

#Using the NetCDF library to examine the contents of a data file
>>> import netCDF4
>>> ds = netCDF4.Dataset("example_data/ggas2014121200_00-18.nc")
>>> for v in ds.variables:
...     print v,
... 
longitude latitude surface time CI SSTK MSL TCC U10 V10 SKT
>>> sst = ds.variables["SSTK"]
>>> print sst
<type 'netCDF4._netCDF4.Variable'>
float32 SSTK(time, surface, latitude, longitude)
    long_name: Sea surface temperature
    units: K
    grid_type: gaussian
    _FillValue: 2e+20
    source: GRIB data
    name: SSTK
    title: Sea surface temperature
    date: 12/12/14
    time: 00:00
unlimited dimensions: time
current shape = (4, 1, 256, 512)
filling off

>>> for d  in sst.dimensions:
...     print d, len(ds.variables[d])
... 
time 4
surface 1
latitude 256
longitude 512
>>> print sst.shape, sst.size
(4, 1, 256, 512) 524288
>>> for attr in sst.ncattrs
long_name = Sea surface temperature
units = K
grid_type = gaussian
_FillValue = 2e+20
source = GRIB data
name = SSTK
title = Sea surface temperature
date = 12/12/14
time = 00:00

#Extracting data and its related coordinate information and metadata (continue from previous)
>>> arr = sst[1, 0, 10:20, 30:35]
>>> print type(arr)
<class 'numpy.ma.core.MaskedArray'>
>>> dims = sst.dimensions
>>> print dims
(u'time', u'surface', u'latitude', u'longitude')
>>> vars = ds.variables
>>> arr_time = vars["time"] [1]
>>> arr_level = vars["surface"] [0]
>>> arr_lats = vars["latitude"] [10:20]
>>> arr_lons = vars["longitude"] [30:35]
>>> for vals in (arr_time, arr_level, arr_lats, arr_lons):
...     print vals
... 
0.25
0.0
[ 82.45532227  81.75363159  81.05194092  80.35023499  79.64852905
  78.94680786  78.2450943   77.54336548  76.84163666  76.13990784]
[ 21.09375   21.796875  22.5       23.203125  23.90625 ]
>>> metadata = {}
>>> for attr in sst.ncattrs():
...     metadata[attr] = getattr(sst, attr)
>>> print metadata
{u'_FillValue': 2e+20, u'date': u'12/12/14', u'name': u'SSTK', u'source': u'GRIB data', u'title': u'Sea surface temperature', u'long_name': u'Sea surface temperature', u'time': u'00:00', u'units': u'K', u'grid_type': u'gaussian'}

#Create NetCDF files with python
#import librarys
import numpy as np
import time as mytime
from numpy.random import uniform
from datetime import datetime, timedelta
from netCDF4 etc

dataset = Dataset('test.nc', 'w', format = 'NETCDF4_CLASSIC')
#then create dimensions
#create variables

#Writing and plotting NetCDF files exercise
>>> def convert_temp(temp):
...     value = temp.strip("+").strip("C").lstrip("0")
...     return float(value)+273.15
... 
>>> file='home/user01/ncas-isc/python/exercises/example_data/sample-serial-temperature-2h.tsv'
>>> infile = 'sample-serial-temperature-2h.tsv'
>>> outfile = 'sensor-data.nc'
>>> from csv import reader
>>> times = []
>>> tempts = []
>>> with open(infile, 'rb') as tsvfile:
...     tsvreader = reader(tsvfile, delimiter = '\t')
...     for row in tsvreader:
...             times.append(convert_time(row[0]))
...             temps.append(convert_temp(row[1]))


file='home/user01/ncas-isc/python/exercises/example_data/sample-serial-temperature-2h.tsv'
???
