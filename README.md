# Classes and Objects

One of the popular approach to solve a programming problem is by creating objects. This is known as Object-Oriented Programming (OOP).

Everything around us is an object: a car, a pencil, a table, a dog, you and me.

A class is a blueprint for the object. For example, if someone is asked to point the similarity between dog, cat, lion and zebra, then people might say that all these are animals which means all of them belongs to a class ‘Animal’.

Every object has states and behavior. Let’s take an example of a class ‘Animal’ and its object ‘dog’. Now as we all know that a dog has states - name,color,breed etc. and behavior - barking, running,fetching,wagging tail etc. In programming, these states are called ‘Variables’ and behavior is called ‘methods or functions’. Now we can define these variables and methods in class ‘Animal’ and can call these methods anytime after creation of it’s object ‘a dog’.

### Defining a class

A class can be defined in python as follows:
```
class MyNewClass:
    pass
```
A class creates a new local namespace where all its attributes are defined. Attributes may be data or functions.

### Creating an object
Classes can also be used to create new object instances (instantiation) of that class. The procedure to create an object is similar to a function call.
```
>>> obj = MyNewClass()

```
This will create a new instance object named `obj`. 

### Object attributes
Attributes of an object may be data (variables) or methods. Method of an object are corresponding functions of that class. Any function object that is a class attribute defines a method for objects of that class.

Consider the example
```
class MyNewClass:
    def newMethod(self):
        pass

>>> obj = MyNewClass()
```
Here, `obj.newMethod()` is the method object.

#### `self` parameter
You may have noticed the `self` parameter in function definition inside the class but, we called the method simply as `obj.newMethod()` without any arguments. It still worked.

This is because, whenever an object calls its method, the object itself is passed as the first argument. So, `obj.newMethod()` translates into `MyNewClass.newMethod(obj)`.


### The __init__() Function
To understand the meaning of classes we have to understand the built-in __init__() function.

All classes have a function called __init__(), which is always executed when the class is being initiated.

Use the __init__() function to assign values to object properties, or other operations that are necessary to do when the object is being created:

The __init__() function in the TSMODEL class loads the dataframe and saves it as one of the attributes to be used in the future.


# Packaging modules
Python packages are mostly built for distributing reusable code, called libraries, between developers.

Python has a packaging system that allows people to distribute their programs and libraries in a standard format that makes it easy for others to install and use them.

In addition to distributing a package, Python also provides a central repository for packages. This repository is known as The Python Package Index (PyPI). People can upload their packages in PyPI and allows others to download, install and use them.

There are various package managers available to download and install packages. One of the popular ones is `pip`. The pip package manager can look into the PyPI repository for the mentioned package name and install it in the local system with a simple command `pip install <PACKAGE_NAME>`.

### Building a python package
Setuptools is the packaging module that allow developers to more easily build and distribute Python packages.

The `setup.py` file is the build script for setuptools. It tells setuptools about your package (such as the name and version) as well as which code files to include in the final package.

#### Structure of a package
Any python code which are to be distributed as a package should have a `__init__.py` file. The following structure should be followed while creating any python package.
```
package_directory/
  example_pkg/
    __init__.py
  setup.py
  LICENSE
  README.md
```
In the above example, the `example_pkg` is the name of the project that is going to packaged. As it can be seen, an empty `__init__.py` file needs to be added inside the project directory. In the `package_directory`, the packaging components like `setup.py`, `LICENSE` and `README.md` files are to be added.

#### Configurations for a package
A few configurations are needed to be added in the `setup.py` inorder to build a package.
1. `install_requires`:
- One of important configs is called `install_requires`. This configuration should be used to specify what dependencies a package minimally needs to run. So, when the package is installed by package managers like pip, this is the specification that is used to install its dependencies.

- In our example, the `install_requires['pandas', 'sklearn']` in the setup.py means that our package requires `pandas` and `sklearn` to run successfully.

2. One another important config is called `python_requires`. If your project only runs on certain Python versions, setting the `python_requires` argument accordingly will prevent pip from installing the package on other Python versions. For example, if the package is for Python 3+ only, write:
```
python_requires='>=3',
```
For example, in our package, we set the `python_requires` argument to `>=3.5` meaning that the package is supported only on python3.5 and above.

3. LICENSE
Every package should include a license file detailing the terms of distribution. It tells others how they can use your project.

4. README.md
All projects should contain a readme file that covers the goal of the project. The most common format is reStructuredText with an "rst" extension, although this is not a requirement; multiple variants of Markdown are supported as well.

5. Other configurations
Other configs like `name`, `version`, `description` and `author` information can be entered as part of the configuration setup.


# References
For more details, 
- Classes: https://www.programiz.com/python-programming/object-oriented-programming
- Packaging: https://packaging.python.org/tutorials/packaging-projects/


