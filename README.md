#[Glide.js](http://jedrzejchalubek.com/glide/)

Glide is responsive and touch-friendly jQuery slider. Based on CSS3 transitions with fallback to older broswers. It's simple, lightweight and fast. Designed to slide, no less, no more.

##Setup

###1. Include jQuery
jQuery is the only dependency. Make sure to include it.

``` html
<script src="http://code.jquery.com/jquery-1.9.1.min.js"></script>
```

###2. Include Glide.js

``` html
<script src="jquery.glide.js"></script>
```

###3. Make necessary markup
Link to slider stylesheet inside document head.

``` html	
<link rel="stylesheet" type="text/css" href="css/style.css">
```
	
Make necessary markup for slider.

``` html
<div class="slider">
  <ul class="slides">
    <li class="slide"></li>
    <li class="slide"></li>
    <li class="slide"></li>
  </ul>
</div>
```

###4. Init
Init our slider on default options ...

``` html
<script>
	$('.slider').glide();
</script>
```
	
… or with custom options

``` html
<script>
	$('.slider').glide({
		autoplay: 5000,
		arrows: 'body',
		nav: 'body'
	});
</script>
```

##Options
Here is list of all available

| Option | Default | Type | Description
|-------|--------|-----|-----
| `autoplay` | `4000` | int/bool | False for turning off autoplay 
| `animationTime` | `500` | int | !!! That option will be use only, when css3 are not suported. If css3 are supported animation time is set in css transitions declaration inside .css file !!!
| `arrows` | `true` | bool/string | Show/hide/appendTo arrows. True for append arrows to slider wrapper. False for not appending arrows. Id or class name (e.g. '.class-name') for appending to specific HTML markup
| `arrowsWrapperClass` | `slider-arrows` | string | Arrows wrapper class
| `arrowMainClass` | `slider-arrow` | string | Main class for both arrows
| `arrowRightClass` | `slider-arrow--right` | string | Right arrow class
| `arrowLeftClass` | `slider-arrow--left` | string | Left arrow class
| `arrowRightText` | `next` | string | Right arrow text
| `arrowLeftText` | `prev` | string | Left arrow text
| `nav` | `true` | bool/string | Show/hide/appendTo bullets navigation. True for append arrows to slider wrapper. False for not appending arrows. Id or class name (e.g. '.class-name') for appending to specific HTML markup.
| `navCenter` | `true` | bool | Center bullet navigation
| `navClass` | `slider-nav` | string | Navigation wrapper class
| `navItemClass` | `slider-nav__item` | string | Navigation item class
| `navCurrentItemClass` | `slider-nav__item--current` | string | Current navigation item class
| `touchDistance` | `60` | int/bool | Minimal touch-swipe distance to call event. False for turning off touch.
| `beforeInit` | `function(){}` | function | Callback before plugin init
| `afterInit` | `function(){}` | function | Callback after plugin init
| `beforeTransition` | `function(){}` | function | Callback before slide change
| `afterTransition` | `function(){}` | function | Callback after slide change

##API

Make glide api instance.

``` js
var glide = $('.slider').glide().data('api_glide');
```


Now, you can use API as bellow.

``` js
glide.jump(3, console.log('Wooo!'));
```

- `.current()` - Returning current slide number
- `.play()` - Starting autoplay
- `.pause()` - Stopping autoplay
- `.next(callback)` - Slide one forward
- `.prev(callback)` - Slide one backward
- `.jump(distance, callback)` - Jump to current slide
- `.nav(target)` - Append navigation to specifed target (eq. 'body', '.class', '#id')
- `.arrows(target)` - Append arrows to specifed target (eq. 'body', '.class', '#id')


##Changelog
`1.0.5` / `25.11.2013`

- Added after and before transition callbacks
- Added after and before init callbacks

`1.0.4` / `17.09.2013`

- Refined swipe event

`1.0.3` / `15.09.2013`

- Code refactoring


`1.0.2` / `04.09.2013`

- Translate3d slides change (thanks to [OwlFonk](https://github.com/OwlFonk) for suggestion)
- Extend API, getter for current slide number


`1.0.1` / `22.08.2013`

- Modularize code
- Some options changes
- Extend API, manually appending navigation and arrows with specifed target

`1.0.0` / `19.08.2013`

- Plugin release
