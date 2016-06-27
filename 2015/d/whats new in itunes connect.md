# whats new in itunes connect

2015

session 302

dave van tassell

engineering manager, itunes store / itunes connect


# localized

- ongoing

# changes

1. app analytics: see related session
2. agreements, tax & banking: unified mac + ios
3. resources & help: support, search, guides will be on the web instead of pdf
 
# my apps

## cleaner organization

> tabs: from 7 to 4 tabs

- app store:
  - app info and versions
  - version release: 
    - auto
    - manual
    - NEW: scheduled (choose date and time)

## pricing re-design

  - pricing: redesign, view price instead of just tier
  - demo

## testflight updates

- internal tester: same team (itunes connect username), 25 slots - no review - latest build
- external tester: email address, 1000 slots - beta app review - choose the build
- demo (testers can now continue to test while new build is in beta app review)
- add install, session and crashes analytics to testflight level
- update limits: 2 to 6 external build a day, from 10 apps to 100, build expiration from 30 to 60, internal testers, external to support 2000 testers per app
- encryption / export compliance: 
  - new plist key `ITSAppUsesNonExemptEncryption`
    - false = no encryption (no non standard), no uploads necessary
    - true = export compliance required
  - `ITSEncryptionExportComplianceCode`: code required, look up in itunes connect 29:01

# user and roles

- account switching
- app siloing
- new roles
  - app manager (technical user is deprecated)
    - create users
    - assign user roles
    - change pricing
    - submit for review
  - developer
    - upload binaries
    - view crash logs
    - view store metadata
  - marketer
    - update store metadata
    - upload promo art
    - request promo codes
  - all
    - internal test flight
    - create in app purchases
    - create achievements
    - create leaderboards
    - view resolution center