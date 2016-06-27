# getting started with multitasking on ipad in ios9 

session 205

peter hajas 
jacob xiao
kurt revis

uikit engineers

jun 9, 2015 at 430pm

presidio

#overview

this is for ipad air 2 only

# multitasking in your app


## adaptivity (ios8)

- horizontal size classes: compact (one column) vs regular (multi column)
- groundwork: iphone 6 plus = one device has two size classes
- this year: ipad multitasking

## slide over

- compact horizontal class
- ipad starts the compact size, user can change the size class

## split view

- side by side

## why adop it?

- lets user get into it and spend more time with other apps

## adding ipad multitasking to your app

new
- create a new project: ipad multitasking enabled by default

existing
1. base sdk: ios 9 (build settings)
2. device orientation, support all (ipad).. think of orientation as bound size change
3. use launch storyboards, exception handled by plist

## how does it work

- old way: bounds = visible bounds
- change: uiwindow not same as screen bounds of app, depends on split view
- transitions: 
  - horizontally compact vs horizontally regular, use size class transitions
  - not all user change becomes size class change
  - use autolayout
  - legibility
    - `uiview.readablecontentguide`, text is always at a legible width
    - `uitableview.celllayoutmarginsfollowreadablewidth`


# changes to uikit for multitasking

## changes

- use traits and size classes, ios8
- not much has changed.. except
- ~~interface orientation~~ vs view.bounds.size.width>.. or regular size class

- rotation = 2 independent changes
  - content resize
  - then rotation
  
- multitasking resizing = just resizing part

## transitions

- ~~instead of responding to rotation and resize~~
- use rotation and resize (traits)

- rotation timeline:
  - setup (size changes happen after-> trait collection did change) willtransition, viewwilltranslate
  - create animation -> animate alongside transition
  - run animation
  - cleanup -> completion
  
- multitask resize timeline
  - setup (size changes happen after)
  - create animation
  - run animation
  - cleanup
  
  - time limited!
  
## windows
  
## presentation

- uipresentationcontroller, supports adaptivity

## keyboard

- keyboard can be shown by another app?!???

# making the most of multitasking 

- design for adaptivity: 
  - universal
  - compact and regular width
  - use adaptivity
  
- 6 strategies

  1 be flexible, dont hardcode sizes

  - try all the multasking cases (slide over, make it bigger, full screen, slid over another app and use splitview, rotate)
  - watch the ui carefully
  - concentrate on layout
  
  2 use autolayout
  
  3 size classes in xcode (interface builder), preview storyboard size class
    asset catalogs
    
  4 adaptivity callbacks (low level)
  
  5 high level api
  
  - adaptive presentation controllers
  - uitableview
  - uicollectionview
  - uistackview
  
  6 split view controller: mail messages notes
  
  
  adaptive photos - sample code

- guidelines

1. the user controls your apps size, app cannot prevent, app cannot cause size change - size changes can happen at any time
2. keep the user oriented.. prevent user from being lost: app has to decide where to go 
3. don't make abrupt changes
4. be smart in new ways (keep track of what the user was doing)
5. especially going from large to small
6. after becoming inactive: maintain same appearance by remembering size and state
7. primary app, secondary app: only primary can see mirroring/external display .. careful about when 2nd app becomes primary, does it make sense to split the screen
8. performance