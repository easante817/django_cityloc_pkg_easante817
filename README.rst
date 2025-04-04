==============
City Locations
==============

City Locations is a Django app that can be installed in an existing Django project
Documentation: https://toddpy-django-cityloc-pkg.readthedocs.io/en/latest/

Installation
------------

1. Add "citylocations" to your INSTALLED_APPS setting in settings.py:
    INSTALLED_APPS = [
        ...
        
        'citylocations',

    ]

2. Include the citylocations URLconf in your project urls.py like this::
    path('', include('citylocations.urls')),

3. Start the development server and visit http://127.0.0.1:8000/
In the django_cityloc_pkg/ folder, create a file named setup.cfg and add the content below.
The setup.cfg file defines the parameters that are used to build your package. These parameters are also used by installation tools to verify dependencies, and used to document supported usages in PyPI.
setup.cfg content:
[metadata]
    name = django_cityloc_pkg
    version = 0.0.1
    description = A Django app about city locations
    author = Author Name
    author_email = authoremail@example.com
    classifiers =
        Environment :: Web Environment
        Framework :: Django
        Framework :: Django :: 3.2
        License :: OSI Approved :: MIT License
        Operating System :: OS Independent
        Programming Language :: Python :: 3.9    
    
    [options]
    include_package_data = true
    packages = find:
    python_requires = >=3.8
    install_requires =
        Django >= 3.2
            
In the django_cityloc_pkg/ folder, create a file named setup.py and add the content below.
The setup.py is the installation entry point used to install your new package, generate distribution files, and more. The details provided here will be used in the PKG-INFO file that will be generated which will contain metadata about your package.
See the additional resources below for a link to the full documentation of what can be included in the setup.py.
Note the long_description argument will hold the full content of the README.rst file we created in the earlier step.
setup.py content:
from setuptools import setup, find_packages

# put the contents of your README file into the long_description
from pathlib import Path
this_directory = Path(__file__).parent
long_description = (this_directory / "README.rst").read_text()

setup(
    long_description=long_description
)
In the django_cityloc_pkg/ folder, create a MANIFEST.in file and add the content below.
The MANIFEST.in file is used to explicitly define which files will be included in your deliverable package. It will contain files such as static assets, templates, README and LICENSE files.  
MANIFEST.in
include LICENSE.txt
include README.rst
recursive-include citylocations/static *
recursive-include citylocations/templates *
In the django_cityloc_pkg/ folder, create a LICENSE.txt file and add the sample license content below.
According to python.org
"Every package should include a license file detailing the terms of distribution. In many jurisdictions, packages without an explicit license can not be legally used or distributed by anyone other than the copyright holder. If you’re unsure which license to choose, you can use resources such as GitHub’s Choose a License or consult a lawyer."
LICENSE.txt content:
Copyright (c) 2016 The Python Packaging Authority (PyPA)

    Permission is hereby granted, free of charge, to any person obtaining a copy of
    this software and associated documentation files (the "Software"), to deal in
    the Software without restriction, including without limitation the rights to
    use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
    of the Software, and to permit persons to whom the Software is furnished to do
    so, subject to the following conditions:
    
    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.
    
    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.