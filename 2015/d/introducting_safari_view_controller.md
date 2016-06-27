# Introducting Safari View Controller

nob hill

Jun 9, 2015 at 1:30 PM

Session 504

tag: #app frameworks

- RICKY MONDELLO, SAFARI / WEBkit enginner
- yongjun zhang, SAFARI / WEBkit enginner

# web content

- app content (html, js, css) 
  - wkwebview is preferred over uiwebview: rectangle around web content
  - new in ios9: securely load file url, data, customer user agent, wkwebsitedatastore (cookies, cache).. enables private browsing
- websites <- section is about this
  - short term browsing
  
  - use safari, new to ios9: there's a back button, first class content
  - safari vc

# safari view controller

- looks like safari
- done (modal), url field is disabled
- features from safari
  - share cookies with safari
  - autofill: password, contact, credit card 
  - safe (different process)
  - safari reader button, which is customizable in ios9
  - share button: system
  - open to safari
  - can set tint color
  - content blocking..
  - safe (different process, security ssl, phishing)
  - progress for loading
  - 

# api

```
SFSafariViewController : UIViewController

SFSafariViewControllerDelegate

init(URL)
```

- share sheet
- done button

# demo

order me some pizza

# Web-based authentication

- oauth: protect user's credential via token
- 2 steps
  1. use sfsafari vc
  - use app delegate with handle open url, inspect response then dismiss if all good