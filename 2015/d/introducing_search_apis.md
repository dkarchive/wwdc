# introducing search apis

> increase app usage and discoverability

session 709

tag: #system frameworks

jun 10, 2015

11am

mission



# presentors

- vipul ved prakash, siri
- dave salim, siri
- jason douglas, siri

# intro

- time spent in apps: 86%, web 14%
- no indexing like web
- developers choose what is indexed, how it is presented
- results show in spotlight and safari (spotlight suggestions)
- ios9: jump to content directly in apps - deeplink 

> app result even appear when app is NOT installed

# examples

## airbnb

- user searches for `napa`
- can go directly into airbnb napa result
- additional metadata for the host (inquiry) - can call 

## linkedin

- contact profile

## health

- steps section

> deep navigation from an app

# app and content discovery

- cloud index: deep links, dvelopers can tag content as public.. if it is used by a lot of people, it goes to apple cloud index, then available to users even if they don't have the app
- apple finds deep links from the web (when content web and app content is mirrored)
- seamless search interface

## examples

- event: event brite
- medical condition: app suggestions


# app search

3 apis

1. `NSUserActivity`: viewed app content, app history
2. `CoreSpotlight`: any app content, low level access to index on device (database api, add and remove items)
3. ~~`Web Markup`: app content on the web (mirrored app/web content)~~


> agenda: deep dive

- speaker: developer on app search


# NSUserActivity 

- introduced on ios8 for handoff
- capture application state and restored later
- ios9: 
  - allow NSUserActivity to be indexed and searched in spotlight/safari
  - add metadata with NSUserActivity
- Example: recipe app, as user is browsing, create NSUserActivity, add metadata. add to on-device index  
- new properties for app search
  - enable capabilities: handoff, search, public indexing
  - attribuets and keywords: titile, keyword, content attribetu set, expiration date
  - restoring on the web.. web page url
  
- create an activity
  - activity type: `com.yummly.browseRecipe`
  - set title, userInfo
  - set properties
  - `activity.becomeCurrent()` // adds to app index
  - can add image (thumbnail data)
  
  - for public content, take a further step

# CoreSpotlight

- new framework: database like api, used by messages mail notes calendar
- `CSSearchableItem` unique item to index
- describe item with properties
- add to index

- example: unique id, image with title, description, domain (group = album)
- then shows up in spotlight, when user taps: same scheme as handoff, but with a different activity type

- maintaining index: change items, delete items (list of ids, list of domain identifiers, all items)

- demo: photos app, indexing titles

- index support for batching, delegate, extension, data protectin classes



