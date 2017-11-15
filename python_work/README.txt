NCAS Introduction to Scientific Computing

Python

cd my-isc-work/python_work

git add README.txt
git commit -m"pythonreadme"
gitpush

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



