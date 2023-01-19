# Python

### Object-oriented Programming in Python

#### Classes and Instances
- Found in many modern languages. 
- Allow us to logically group data (attributes) and functions (methods) in a way that is easy to reuse.
- Class is a blueprint for objects. 
- Instance variables: contain data unique to each instance. 

Example:
```python
class Employee:
  
  # special 'init' method - like a constructor
  def __init__(self, first, last, pay):
    self.first = first
    self.last = last
    self.pay = pay
    self.email = first + '.' + last + '@company.com'

  # imp: remember to have 'self' as the first arg in class methods
  def fullname(self):
    return '{} {}'.format(self.first, self.last)

# Creating instances of the Employee class:
emp_1 = Employee('Corey', 'Schafer', 5000)
emp_2 = Employee('Test', 'User', 6000)

# Imp: the following lines both do the same thing:

emp_1.fullname() # passes emp_1 as self implicitly
Employee.fullname(emp_1) # explicitly pass emp_1 as self

```

#### Class Variables
- Variables that are shared among all instances of a class.
- Data that is the same for each instance can be put in a class variable.

```


### Performing an HTTP Request in Python

First, install `requests` library:
```shell
pip install requests
```

Then:
```python
import requests

# GET request
response = requests.get('https://pythonexamples.org/python-basic-examples/')

# convert json response to Python dictionary
response_dict = response.json()
```

More features of Python `requests` library can be found here: https://pythonexamples.org/python-requests-http-get/
