# What's new in managing Apple devices


Tag: #distribution

Session 301

Nob Hill

2015, Jun 9

Tuesday 11AM

# Presentor

todd fernandez
senior manager, device mgmt

deploy and manage devices

education + enterprise
school + business

volume

get started without going through setup


# enrollment

through device enrollment program

avail in 26 countries

four-hour turnardound time to get device replaced in program

enrollment optimization

mdm server
await_device_configured

ios or mac

account creation
passcode policy
standard vs admin account (hidden: education)


`SetupConfiguration` command

ios9 automated enrollment
- enroll device without user interaction
- based on dep settings -> gets straight to homescreen (shared device deployment)

setup assistant: touch id, apple pay, zoom, android migration

server: `MDMServiceConfig`

helps user with profile url

# distribution

app types: app store, b2b, enterprise, ad-hoc

apple configurator

purchasing vpp management distribution
volume purchasign program
expanded to 26 countries

multination app assigment: purchase in one country, distribute where app is used..
vpp can assign app to devices: *no apple id required*, managed by admin/mdm server 

purchased on vpp store
can be assigned to user/device, can be revoked and reassigned
smootih migration
requires mdm server or apple confiugrator

app developer need to opt in (itunes connect)
update receipt checking - check for device/user assignment
store app data in the cloud - for shared development, can use cloudkit

os x server: caching server
os update and apps

on demand app reousrces
cloudkit data
icloud drive docs

data is encrypted

