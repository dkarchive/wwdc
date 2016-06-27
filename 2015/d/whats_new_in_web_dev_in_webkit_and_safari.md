# whats new in web dev in webkit and safari

 #developer tools #framework

- tuesday jun 9, 9am in mission - session 501

presenting: 

- brent fulgham, webkit engineer
- chris young-zawada, senior front end dev

topics:

intro to webkit
webkit enhancements in safari
creating amazing experiences on mac and ios

# intro to webkit

- web engine
- also used in app store app, itunes, 2, mail.. more
- same for ios and osx

webkit:

- safari
- wkwebview
- javscriptcore (automation)


# webkit enhancements in safari

 
## new layout and rendering features

### backdrop

- backdrop effects (blur): in ios, osx
- can add to webpage to be part of native ui
  - ~~translucent~~
  - ~~css filter~~
  - ~~hacks~~: cannot animate, difficult to change the blur effect
  - `backdrop-filter: filter` declare backdrop filter effects in css (proposed as standard)
  
  ```
  -webkit-backdrop-filter: blur(10px)
  ```

  - can invert colors
  - combine with grayscale
  - can be overlayed on dynamic background (video)

### paged scrolling in js

- itunes style banners, photos app - move across entire block, one at a time
- hacks have performance issues (complicated js on each frame of scrolling)  

- scroll snap points
- declare target scroll positions in css
- css standard
- each swipe takes the entire width, no matter how strong the swipe is you land in boundary: edge will bounce back into place

```
-webkit-scroll-snap-type: mandatory
-webkit-scroll-snap-point-x: repeat(300px)
```

there is also `scroll-snap-point-y`

#### non uniform elements

- variable unit (width)

```
scroll-snap-destination: 50% 50% 
scroll-snap-coordinate: 50% 50% //center
```

### demo

- photos app
- add backdrop filter (blur)  
- add scroll snap point

### best practices

- ...

## modern javascript updates es6

- `es6`
- template literals 

```
console.log(`Value: ${a} and ${b}.`);
```

- object literal property syntax
- prototype syntax
- class syntax

## new css features

- unprefixed properties and values (-webkit less version)
- detecting feature support
  - ~~manually detecture feature support~~
  - `@support(condition)`
  
  ```
  @support(-webkit-initial-snapdestination) {
  }
  ```
  - reducting repetition: `matches`
  
  ```
  .default :matches(.def, .bracket, .operator, .variable) {
    color: red;
  ```
  
 

# creating amazing experiences on mac and ios

- adopt features that are unique to mac and ios
- airplay video for osx (same api as ios)
- multitask (ipad)
  - responsive design, see corresponding session
- picture in picture
  - presentation mode (fullscreen)
  - inline 
  - picture in picture (new)
    - page may not be obscured while video is playing
    - use http live streaming (hls), match resolution with size of display
    - see corresponding session wednesday
- force touch
  - new level of click: in safari dictionary, preview link
  - mousedown, mouseup
  - mouseforcewillbegin, mouseforcedown, mouseforceup (and mouseforcechanged)
- demo
