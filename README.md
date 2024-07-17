# AI, Machine Learning and Python
## AI
## Machine Learning
## Python Basics
- uses dynamic typing
- `a = 1 + 1` and `type(a)`
- Single quote or double quote strings
- `\t` and `\n`in strings
- `myString[0] or myString[-1]`
- `mystring[start:stop:step]` i.e `mystring[2:7:2]`
- `mystring[2:]` and `mystring[:3]`
- Strings are immutable
- `'a' * 10`is valid
- Refer to [this](https://github.com/Pierian-Data/Complete-Python-3-Bootcamp/tree/master).
```
'x'.upper();
'hi there are'.split()
print('This is house of commons: {}'.format('Torries'))
print('This is house of commons: {x}'.format(x = 'Torries')) 
# or user index
print('This is my ten-character, two-decimal number:{0:10.2f}'.format(13.579))
name = 'Fred'
print(f"He said his name is {name}.")
```
- len for string length

#### list
```
mylist = ['one', 'two', 'three']
newlist = mylist + yourlist
newlist[0] = 'ONE'
newlist.append('seven')
newlist.pop() # removes the last item
newlist.pop(2) # pop from index 2
newlist.sort() # carried out in-place. no return value
newlist.reverse()'
```
#### dictionary
- key-value structure
- same as map in java
```
dic = {'apple': 2.99, 'orange': 3.99}
dic = {'apple': 2.99, 'orange': 3.99, 'melon': [1, 2, 34]}
dic['apple']
dic['lemon'] = 4.99 # new pair. we can override the value as well
dic.keys()
dic.values(){
```
#### tuples
- similar to list but is immutable
- uses parentheses `()`
- important use case is when you pass the object and don't want it get changed.
- one can have list of tuples
```
t = (1, 3, 4)
t[0]
t.count('a')

x1,x2 = self.cordinate1
```
#### sets
```
myset = set()
myset.add(1)
uniqueval = set('Mississipi')
```

#### boolean
- True, False
#### I/O with Basic files
```
# works only in jupiter
%%writefile myfile.txt
hello there, how is everything

myfile = open('myfile.txt')
myfile.read()
myfile.seek(0)
myfile.read()
myfiel.seek(0)
myfile.readlines()
myfile.close()

# To avoid manual closing use with
with open('myfile', mode='r') as f: 
     contents = f.read()
# mode read (default), write, append only
pwd 
```
- use shift + tab to see signature
#### Control flow and loop
```
if some_condition:
elif: other_conditions
else:

for item in items_list:
  print(item);

mylist = [(1,2), (4,5), (7,8)]
for (a,b) in mylist:
  print(a)
  print(b)
  
for key,value in mydictionary.items():
  print(key)
  print(value)

while some_conditions:
  # do something
else:
  # do something else
```
- break, continue, pass
```
for item in x:
  # comment
  pass

mytext = 'karl'
for letter in mytext:
  if letter == 'a'
    continue
    # break check it out
  print(letter)
```
- Useful operations
```
for num in range(10): # range(3,10) # range(0,11,2) with steps

workd = 'Ahmad'
for item in enumerate(word):
  print(item)
  
for item in zip(list1,list2, list3):
  print(item)

2 in [1,2,3,6] # in string, in dictionary, in 
> True

min(list1)
max(list1)

from random import shuffle
shuffle(mylist) # in place and no return


from random import randint

randint(0,10)

val = input('Enter a number here')

float(val)
int(val)
```

- List comprehension
```
mytext = 'ahmad'

mylist = [letter for letter in mytext]
mylist = [num**2 for num in range(0,11)]
mylist = [num for num in range(0,11) if num%2==0]

celcius = [0, 10, 25, 30]
fahrenheit = [ ((9/5)*x + 32) for x in celcius]

#nested loop
for x ...
  for y ....
```

#### Methods and functions
- `help ('sfa'.split)`
- shift + tab in jypitor
```
def name_of_function(name): # snake case, in object oriented use camelcase
  """
  commenting
  """
  print("hello" + name)

def add_function(num1,num2): # snake case, in object oriented use camelcase
  """
  commenting
  """
  return num1 + num2


def calc_interest(sum): # check type explicitely as python is dynamic typed
  """
  here tere
  """
  rate = 0.05
  print(f'passed value: {sum}')
  return sum*rate
  
```
- Tuple unpacking with functions
    - tuples as return can be unpacked in place
```
def employee_check(work_hours):
    
    # Set some max value to intially beat, like zero hours
    current_max = 0
    # Set some empty value before the loop
    employee_of_month = ''
    
    for employee,hours in work_hours:
        if hours > current_max:
            current_max = hours
            employee_of_month = employee
        else:
            pass
    
    # Notice the indentation here
    return (employee_of_month,current_max)
    
name,hours = employee_check(work_hours)
```
- *args and **kwargs (key-word)
```
def myfunc(*args): # As many as possible args myfunc(*nums)
  return sum(args) * 0.05


def myfunc(*args, **kwargs):
    if 'fruit' and 'juice' in kwargs:
        print(f"I like {' and '.join(args)} and my favorite fruit is {kwargs['fruit']}")
        print(f"May I have some {kwargs['juice']} juice?")
    else:
        pass
        
myfunc('eggs','spam',fruit='cherries',juice='orange')
```
- Lambda expression, Map, and Filter functions
```
def square(num):
  return num**2
my_nums = [1,2,3,4,5]

list(map(square, my_nums) # func without paranthesis, as map will call it later

def check_even(num):
  return num%2 == 0

list(filter(check_even, my_nums))

for n in filter(check_even, my_nums):
  print(n)
```
- Lambda expression:
```
list(map(lambda num: num**2, my_nums))
```

- Nested Statements and Scopes
    - LEGB Rule:
        - Local (local inside function), Enclosing function locals (func inside func), Global(module), Built-in (Python)
        - ```
      name = 'Global'
      def greet():
        name = 'Rashed'
        def hello():
          name = 'local'
          print(name)
        hello()
      ```
        - Above global, is built-in
    - using `global` keyword, one can access global variable and change the value inside the local func
        - avoid this, and go for passing the global var to the function
#### OOPS in Python
```
class NameOfClass():
  pi = 3.14
  def __init__(self,param1=1,param2):
    self.param1 = param1
    self.param2 ...
  def some_method(self):
    print(self.param1)
```
- `Circle.pi` or `self.pi`
- type(list) --> list class
- `newClass.param1` and `newClass.bark()`

##### Inheritance and Polymorphism
```
class Dog(Animal):
  def __init__(self):
    Animal.__init__(self)
    print("Dog created")
```
- `myDog.eat()`
- Each method will have self in param
- Polymorphism
  - Cat and Dog class and then iterate them with pet (each has same method signature)
##### Magic/Dunder methods
```
    def __str__(self):
        return f"{self.title} by {self.author}"
    def __len__(self)
        return self.pages
    def __del__(self)
```
- `del variable`

#### Modules and packages
- PyPi is to python as npm is to nodejs
- Standard libraries
- Write own modules and package
  - package is a collection of modules. A module is .py script
    ```
    from mypackage import somemainscript
    from mypackage.subpackage import mysubscript
    
    somemainscript.main_report()
    mysubscript.sub_repot()
    ```
  - In the above, mypackage and subpackage are just two folders containing __init__.py in each
- Built-in variable `__name__` and `__main__` for organizing code. Check chatgpt for clarification

#### Error and Exception Handling
- try, except, and finally
```
try:
  f = open('testfile', 'w')
  f.write("write a test line")
  ....
except TypeError:
  print("There was a type error")
except:
  print("There was an exception error")
finally:
  print("It runs always")
  ....
else
```

#### Python Unit Testing
- pylint: reports back possible issues, PEP8
- unittest: native lib for unit testing
```
class TestCap(unittest.TestCase):
  def test_one_word(self):
    text = 'python'
    result = cap.cap_text(text)
    self.assertEqual(result, 'Python')
    
if __name__ == '__main__'
  unittest.main()
```

#### Python Decorator
- Add more functionality to a function using @ operator
```
def hello():
  print("hell")
  
  def greet():
    print("greet")
  
  return greet
```
```
def new_decorator_func(func):
  print(func())
```

```
@new_decorator_func
def func1():
  print...
```
- Used extensively by frameworks like [Flask](https://flask.palletsprojects.com/en/3.0.x/), [Django](https://www.djangoproject.com/)

#### Python Generator
- Generates values overtime instead of at once
- Memory efficient
```
def create_cubes(n):
  for x in range(n):
    yield x**3
    
    
for x in create_cubes(100):
  print(x)
```
```
g = create_cubes(10)

print(next(g))

s = 'Enayat'
# convert this to gen
s_iter = iter(s)
```
- example of Febonacci sequence
```
def gen_fibon(n):
  a = 1
  b = 1
  
  for i in range(n):
    yeild a
    a,b = b,a+b
```

#### Advanced Python Modules
- Collection:
```
from collections import Counter
c = Counter(mylist)
c.most_common()
list(c) # get all the unique values

from collections import defaultdict

from collections form namedtuple # call the values by index or by a name for readibility
```
- , math, 
- OS: Opening and reading files and folders
```
pwd
f = open('practice.txt', 'w+')
f.write('This is me')
f.close()
```

```
import os
os.getcwd()
os.listdir()
os.walk

for folder, sub_folders,files in os.walk(file_path)

os.listdir('/sample_data')
os.unlink(path)
os.rmdir(path)


import shutil
shutil.move(src,dst)
shutil.rmtree(path) # dangerous, remove permanently

alternative: pip3 install send2trash
```

- Datetime:
```
import datetime
datetime.time(2,20,1,20)
today = datetime.date.today()
today.day
today.month
today.year

from datetime import datetime
mydatetime = datetime(2021,18,3,4,2)
mydatetime.replace(year=2022)

result = date1 - date2
datetime.timedelta
```
- Math, Random:
  - i.e math.e, math.log(math.e)
  - random.gauss(mu=0,sigma=100) # gaussian distribution
- Debugger:
  ```
  import pdb
  
  x = 'a'
  y = 1
  z = 5
  
  result_one = y + z
  
  pdb.set_trace()
  
  result_two = y + x
  ```
  - Run and check what assigned to which value at tracing point
  - use q to quit
- Regex:
  - `r"(\d\d\d)-\d\d\d-\d\d\d\d"` --> (555)-555-555-5555
  - `r"(\d{3})-\d{3}-\d{4}"` --> (555)-555-555-5555 using quantifiers
  - \d, \w, \s (white space), \D (non-digits), \W, \S
  - Quantifiers: {3}, + (one or more times i.e \w+), {2,4} (range between 2 and 4), {3,} (3 or more), * (zero or more times), ? (once or none i.e plurals?)
  ```
  import re
  text = "there the was a phone number was"
  pattern = 'phone'
  match = re.search(pattern, text
  
  match.span()
  match.start()
  
  for match in re.finditer('phone',text)
  
  phone_pattern = re.compile(r'(\d{3})-(\d{3})-(\d{4})') # having three groups indicated by ()
  results = re.search(phone_pattern,text)
  results.group()
  results.groupt(1) --> 555 # indexing at one instead of 0 
  ```
  - or, wildcard
  ```
  re.search(r'cat|dog', 'This is a cat')
  re.findall(r'at', 'The cat at sat') vs re.findall(r'.at', 'The cat at sat') vs re.findall(r'..at', 'The cat at sat')
  re.findall(r'ˆ\d', '1 is a number') # text starts with digit
  re.findall(r'\d$', '1 is a number') # text ends with digit
  
  
  phrase = 'there are 3 number in 34 inside 5 this sentence'
  pattern = r'[ˆ\d]+ # exclude any digits using []
  re.findall(pattern,phrase)
  re.findall(r'[ˆ!.?]+', 'There is! how are you? Good.')
  
  text = 'Only find the hpye-words in this sentence'
  patther = r'[\w]+-[\w]+'
  ```
- Timing your python code for code quality evaluation
  ```
    def func_one(n):
      return [str(num) for num in range(n)]
    
    def func_two(n):
      return list(map(str, range(n)))
    
    import time
    
    start_time = time.time()
    result = func_one(1000000)
    end_time = time.time()
    
    elapsed_time = end_time - start_time # do it for func two and compare
  ```
  - The above setup is simple and doesn't reflect proper value for smaller values
  - Alternative with more efficiency:
  ```
  import timeit
  stmt = ```
          func_ont(100)
          ```
  setup = ```
           def func_one(n):
              return [str(num) for num in range(n)]
          ```
  timeit.timeit(stmt, setup, number=100000)
  # Do it for func_two and compare
  ```
  - Simpler setup
  ```
    %%timeit
    func_one()
  ```
- Zip/Unzipping:
  ```
  f = open('one.txt')
  f.write('One File')
  f.close()
  
  import zipfile
  comp_file = zipfile.ZipFile('comp_file.zip', 'w')
  comp_file.write('one.txt', compress_type=zipfile.ZIP_DEFLATED)
  comp_file.write('two.txt', compress_type=zipfile.ZIP_DEFLATED)
  comp_file.close()
  
  # To Extract
  zip_object = zipfile.ZipFile('comp_file.zip', 'r')
  zip_object.extractAll('extracted_content')
  ```
  - compress an entire folder
  ```
  import shutil
  dir_to_zip = '/aa/aadf/extracted_content'
  output_filename = 'example'
  shutil.make_archive(output_filename, 'zip', dir_to_zip)
  
  shutil.unpack_archive('example.zip', 'final_upzip', 'zip')
  ```
#### Web scraping - downloading images etc
`
pip3 install requests
pip3 install lxml
pip3 install bs4
`
```
import requests
result = requests.get("http://www.example.com")
import bs4
soup = bs4.BeautifulSoup(result.text, "lxml")
soup.select('title')[0].getText() # use CSS syntax for accessing html elements
soup.select('.sampleClass')
soup.select('img')
computer = soup.select('.thumbimage')[0]
computer['src']
<img src="dxdfadfa">

image_link = request.get("link")

f = open('downloaded_image', 'wb')
f.write(image_link.content)
f.close()
## you get the jpg image in working directory


base_url = 'http://www.bookscrape.com/page-{}.html'

res = requests.get(base_url.format(20))
soup = bs4.BeautifulSoup(res.text, 'lxml')

products = soup.select(".product_prood")
example = products0[0]
example.select(".star-rating.Three")
```

#### Working with Images in Python
- `pip3 install pillow`
```
from PIL import Image

mac = Image.open('example.jpg')
type(mac)
mac.show()
mac.size
mac.crop((0,0,100,100))
mac.resize(500, 500)
```
- RGBA (Red, Green, Blue, Alpha)
```
mac.putalpha(0) # complete white transparent
mac.paste(mask, (0,0), mask)
mac.save("upated-mac.png")
```

#### Working with PDFs and Spreadsheet CSV
- Pandas library used by data science too for data visualization and analysis
- Openpyxl library
- Google sheets Python API
```
import csv
# Open file
data = open('example.csv', encoding='utf-8')

csv_data = csv.reader(data)
data_lines = list(csv_data)
data_lines[10][2]
#
```
- PDF reading
  - PyPDF2
    - read a page
    - Add text to the end or a new page

#### Email with Python
- Steps: connect to email server --> confirm connection --> setting a protocol --> logging on --> and sending
- In python built-in `smtplib` used
- Each mail provider has its own SMTP server i.e smtp.gmail.com
```
import smtplib

smtp_object = smtp.SMTP('smtp.gmail.com', 587)
# creates the connect
smtp_object.ehlo() 

# Encryption
smtp_object.starttls()

import getpass
password = getpass.getpass('What is your password: ')

# Create App password for your gmail account

# 
email = getpass.getpass('Your email: ')
smtp_object.login(email,password) # Enter your app password

from_address = email
to_address = email
subject = input('Input your subject: ')

message = input('Enter the body message: ')
msg = "Subject: "+subject+'\n'+message
smtp_object.sendmail(from_address,to_address,msg)

smtp_object.quit()
```
- Receiving Email using Python (reading the inbox)
  - `imaplib` and `email` lib
```
import imaplib
M = imaplib.IMAP4_SSL('imap.gmail.com')
import getpass
email = getpass.getpass('Your email: ')
password = getpass.getpass('What is your password: ')

M.login(email,password)
M.list()
M.select('inbox')

typ, data = M.serach(None, 'SUBJECT ""NEW TEST PYTHON')
email_id = data[0]
result, email_data = M.fetch(email_id, '(RFC822)')
raw_email = email_data[0][1]
raw_email_string = raw_email.decode('utf-8')

import email
email_message = email.message_from_string(raw_email_string)

for part in email_message.walt():
  if part.get_contect_type() == 'text/plain':
    body = part.get_payload(decode=True)
    print(body)
```

#### Advanced Python Objects
- Advance Numbers: hex(...), bin(...), pow(...), abs(...), round(...)
- Advanced String: capitalize(...), upper(...), count('o'), center(...)
- Advanced Sets: 
```
s = set()
s.add(1)
s.clear()
sc = s.copy()
sc.add(3)
s.difference(sc)
s.difference_update(s2)
s.discard(2)

# intersection
s1.intersection(s2) and s1.intersection_update()
s1.isdisjoint(s2)
s1.issubset(s2)
s2.issuperset(s1)
s1.symmatric_difference(s2)
s1.union(s2)
s1.update(s2)
```
- Advanced Dictionaries:
```
d = {'k1':1, 'k2':2}
# Dictionary comprehension like list
{x:x**2 for x in range(10)}

for k in d.iteritems():
  print(k) # prints key and value

for v in d.values():
  print(v)

d.viewitems()
```
- Advanced Lists:
```
l = [1,2,3]
l.append(4)
l.count()
l.extend()

x = [4,5]
l.append(x) vs x.extent([4,5])
l.index(2)
l.insert(2, 'value')
l.pop()
l.pop(2)
l.remove('inserted') # remove the first instance
l.reverse()
l.sort()
```

#### GUIs in python
- NbViewer, PyGame
- For Web apps, better use Javascript frameworks like react and angular
```
import ipywidgets from interact, interactive, fixed
import ipywidgets as widgets

def func(x):
  return x**2
interact(func,x=10)

interact(func,x=True)


@interact(x=True,y=1.0) # y=fixed(1.0)
def g(x,y):
  return (x,y)
  
w = widgets.IntSlilder()

from IPython.display import display
display(w)
w.close()
w.keys
widgets.jslink((a,'value'), (b, 'value'))

```
- List of possible widgets
```
for item in widgets.Widget.widget_types.items():
  print(item[0])
```
- Widgets styling and layouts
```
w.layout.margin = 'auto'
w.layout.height = '75px'
w.Button(description='Ordinary Button', button_style='danger'
```
- Advanced widgets
  - NumPy 
  - Matplotlib
  - SciPy
  - course: Python for Datascience and ML Bootcamp
  - Refer [to](https://github.com/Pierian-Data/Complete-Python-3-Bootcamp/blob/master/19-Bonus%20Material%20-%20Introduction%20to%20GUIs/06-Custom%20Widget.ipynb) to understand a visualization of lorenz equation
```
%matplotlib inline
from ipywidgets import interact, interactive
from IPython.display import clear_output, display, HTML

import numpy as np
from scipy import integrate

from matplotlib import pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from matplotlib.colors import cnames
from matplotlib import animation

```
#### Final Capstone Project
- Do it in the free time
### Python Setup
- `python3 --version` in macos
- `pip3`
- Install [JupyterLab](https://jupyter.org/install) using pip3 and start it `jupyter lab`
- Install pyscopg `pip3 install pyscopg`
    - `pip3` is a package manager
    - `python3` is the command used to run python code
- When we have Postgres.App instead of an installed Postgres, we need to make sure JupyterLab is able to find libpq
- DYLD_LIBRARY_PATH is an environment variable used on macOS to specify additional directories to search for dynamic libraries.
  In the context of Postgres.App, which is a self-contained application bundle that includes the PostgreSQL database server and related tools,
  setting DYLD_LIBRARY_PATH allows the operating system to locate the PostgreSQL dynamic library (libpq) bundled with Postgres.App.
```
export DYLD_LIBRARY_PATH=/Applications/Postgres.app/Contents/Versions/<version>/lib:$DYLD_LIBRARY_PATH
export DYLD_LIBRARY_PATH=/Applications/Postgres.app/Contents/Versions/16/lib:$DYLD_LIBRARY_PATH
```
- Restart jupyterlab and Proceed with Notebook coding:
```
[1] import psycopg as pg;

[2] try:
    connection = pg.connect(
        user="postgres",
        password="",
        host="localhost",
        port="5432",
        dbname="dvdrental"
    )
    print("Connected to the database.")
except (Exception, pg.Error) as error:
    print("Error while connecting to PostgreSQL:", error)
    
[3] cur = connection.cursor()
[4] cur.execute("SELECT * FROM payment")
[5] data = cur.fetchmany(5)
[6] data[0][4]
[7dCo] connection.close()
```

## Resources Links
- Training github repo [here](https://github.com/Pierian-Data/Complete-Python-3-Bootcamp.git)
- 