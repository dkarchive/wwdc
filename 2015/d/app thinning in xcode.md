# app thinning in xcode

developer tools

session 404

# how app distribution is being improved

- app distribution today

xcode - developer signs, app store resigns - app store

- what's in an app

  1. executable code
  2. resources
  
  - some have more code than resources and vice versa
  
  - executable code can have 32-bit / 64-bit slices or armv7 / armv7s / arm64
  
  - resources are 1x, 2x, 3x
  
  - graphics technologies (texture map): OpenGL es low an high quality / metal lq and hq
  
  - audio 96kb / 192kb bitrate
  
  - other data

- app slicing: load right assets for specific device, but move this into the store

  - ipad mini: armv7, 1x ipad, opengl es lq, 96kb audio, other data
  - iphone 6 plus: arm64, 3x iphone, metal hq, 192kb audio, other data

- user workflow is the same (upload one universal bundle
- slicing happens in the store, builds separate ipa's

- size savings (demo bots)
  - universal 74mb
  - thin ~22mb (19 variants get created)
  
- can we do better: on demand resources
  - required, always needed
    - executable code
    - basic interface and artwork
  - optional, maybe be needed later
    - advanced level in a a game
    - tutorial that the user only watches once
    - audio for instruments

  - partition by the developer, what is needed at any given time (shared vs levels)
  
  - device caches and downloads odr as it is being requested, can be cleared when device runs out of space
  
  > what happens in the ui when downloading is in progress?
  
  - build asset packs in xcode
  
  - hosted by the app store
  
  - further app slicing: ~14mb
  
  - advantages
    - support devices with constrained space
    - shorter download
    - easier to stay within ota limits
  
# how to minimize your app's footprint

- asset slicing
- seamless with xcode
- post process of assset catalog and executable files
- developer: use asset catalogs (loose resources are not thinned)

- content in asset catalog:
  - named images (existing): png, jpg 
  - named data (new): arbitrary file content classified by hardware capabilities (NSDataSet)
  - sprite atlases: combines asset catalogs and spritkit
  
- asset catalog to app thinning: done in post processing

- cataloging efficiently is key: organization, less redundancy - don't leave assets as universal if they are only used on one device family


# what this means for your workflow

`create - build - distribute`

## create

1. create through asset catalog in xcode
2. asset catalogs and external toolchains: export image and data sets from existing pipelines, using xcasset source artifact format (simple folder folder structure and json markup)
  - requires xcasset folder reference
  - no limitations on file hierarchy
  - at build time, xcode build generates the project integration 
  
## build

- build and run automatically things resources for the active run destination
- new option in asset catalog compiler options, this speeds up iterative developement

## distribution

automatic 

- app store 
- testflight 
- adhoc/enterprise (hosted)
  - organizer can create specific ipa
  - ota: manifest plist with urls for each variant 
- xcode server / ci

