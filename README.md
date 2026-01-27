# ci-advance

Create: python funnction
File: app1.py
create a function name add
it should take two parameters
it should return the sum

def add(a,b){
   return a+b
}

write Test cases
File: test_app1.py
use pytest
import the add function
weite atleast 2 test cases

from app import add
def test_add_positive():
assert add(5,3)==8

def test_add_negative():
assert add(-2,-4)== -6

create requirements.txt

File: requirements.txt
add the required testing dependecy
pytest


Run Test Locally

Students must run:

pip install -r requiremnt.txt
pytest

take a screenshot of:
successfull test execution

github actions in yaml

on:
    push:
    branches: ["main"]
    pull_request:
    branches:["main]

    jobs:
    test:
        runs-on:ubuntu-lastest

    steps:
    -name:Checkout code
    uses:action/checkout@v4

    -name: set up python
    uses:actions/setup-python@v5
    with:
    python-version:"31.10

    -name: install dependencies
    run:
        python -m pip install
        pip install -r requirement.txt

    -name:Run tests
        run:
            pytest