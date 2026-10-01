
carefully write me a python processor that includes all code into one file

it's similar to c/cpp's preprocessor's #include feature, which simply copy and paste
the content of entire file into a target file

cli parameters/flags:

-i --input it will trace all the way to
-o --output

preprocessor.py -i main.py  

context: 


file examples:

(main.py) 
py```

from another import *

```

(another.py) 
py```
from tools import *

def is_string(val):
    return isinstance(val, str):

def main():
    print(f'Hello, {double_string}')
```


(tools.py) 
py```
from another import *

def double_string(s):
    if is_string(s)
        return str(int(s) * 2)
    return s # won't return if it's not a string
```

principals/values:

1. write everything inside one file, which includes the compiler's source itself. 
   you can have several files for such as docs, test, changelogs etc. outside the source file, 
   but not the compiler itself

2. ide support is the key. the purpose of using wildcard import instead 

3. write it smart, functioning well, neat (however, not that important as other values), 
   not just write it, not just a working preprocessor, as this should be easy to implement 
   
4. make sure to add comments and documentations properly.

help me read this documentation, check, carefully understand my needs and and improve the wording (in terms of prompt engineering) and add more details/suggestions/recommendations in terms of features, functions, rules, etc. read my requests and carefully understand the needs, then implement 


! read and analyze the overall task of what I should do basically and explain me carefully what to do next