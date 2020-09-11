# python-django-tips

This is my personal notes about Python Django Tips that I found on the Internet and books that I read. Reference will be mentioned at the bottom.

1. Make your code as readable as possible:
- Avoid abbreviating variable names. 
- Write out your function argument names. 
- Document your classes and methods. 
- Comment your code. 
- Refactor repeated lines of code into reusable functions or methods. 
- Keep functions and methods short. A good rule of thumb is that scrolling should not be necessary to read an entire function or method.

2. PEP 8 describes coding conventions such as: 
- Use 4 spaces per indentation level.
- Separate top-level function and class definitions with two blank lines.
- Method definitions inside a class are separated by a single blank line.

3. "Use Black to format Python Code". Black is an uncompromising Python code formatter created by Łukasz Langa. By using it, we give up our control over the minutiae of hand-wrangling code into legibility, and in return it gives us speed and determinism in how our code will look. https://github.com/psf/black

4. "Use Flake8 for Checking Code Quality". 
Created by Tarek Ziadé and now maintained by the PyCQA group, Flake8 is a very useful command-line tool for checking coding style, quality, and logic errors in projects. Use while developing locally and as a component of Continuous Integration. See github.com/PyCQA/flake8

5. "Aymeric Augustin on Line Length Issues". Django core developer Aymeric Augustin says, “Fitting the code in 79 columns is never a good reason to pick worse names for variables, functions, and classes. It’s much more important to have readable variable names than to fit in an arbitrary limit of hardware from three decades ago.”

6. PEP 8 suggests that imports should be grouped in the following order:
```
 1. Standard library imports
 2. Related third-party imports
 3. Local application or library-specific imports

 And The import order in a Django project is:
 1. Standard library imports.
 2. Imports from core Django.
 3. Imports from third-party apps including those unrelated to Django.
 4. Imports from the apps that you created as part of your Django project.
```
&nbsp;&nbsp;&nbsp;&nbsp;Good Python Imports
```
# Stdlib imports
from math import sqrt
from os.path import abspath

# Core Django imports
from django.db import models
from django.utils.translation import gettext_lazy as _

# Third-party app imports
from django_extensions.db.models import TimeStampedModel 

# Imports from your apps
from splits.models import BananaSplit
```

&nbsp;&nbsp;&nbsp;&nbsp;Relative Python Imports

```
# cones/views.py
from django.views.generic import CreateView

# Relative imports of the 'cones' package
from .models import WaffleCone from .forms import WaffleConeForm

# absolute import from the 'core' package
from core.views import FoodMixin
class WaffleConeCreateView(FoodMixin, CreateView): 
      model = WaffleCone
      form_class = WaffleConeForm
```
 
7. "isort for Sorting Imports".  
The isort Python library sorts your imports so we don’t have to. It imports alphabet- ically and automatically separates our imports into sections and by type.
https://github.com/PyCQA/isort

8. 

# Reference
["Two Scoops of Django 3.x: Best Practices for the Django Web Framework"](https://www.feldroy.com/products/two-scoops-of-django-3-x)
