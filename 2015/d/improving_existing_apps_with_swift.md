# improving existing apps with swift

getting swifty with it
tag: #developer tools

pacific heights
jun 9, 2015 at 3:30pm
session 403

# presentors

- Woddy L, whale in the sea of swift

# elements app

- modernize it using swift
- mix and match
- modernizing ui
- structs
- map/reduce

- create new code
- call it from objc

# mix and match

class design: 
- use an extension (instead of objc category)

bridging header 
- import manually

+ generated header (exits in derived data)

call it from objc 
import generated header

`class extension`

# swift structs

# playgrounds for prototyping

- experiment 

- create playground from code (copy)

# availability


swift 2.0 supports availability

classic way 
do not use if `respondsToSelector()`

new way
if #available(iOS 8.3, *)
this tells you at compile time if it works

# live search

using swift filter