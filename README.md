#ScrollMagic is awesome!!

![ScrollMagic](https://media.licdn.com/mpr/mpr/AAEAAQAAAAAAAANPAAAAJGM3ZWZkZmE5LWNiNGUtNDZkMS05ZGY5LTEwMzNhN2IwMDM4OQ.png)

[Demo Page](http://typist-norman-21531.bitballoon.com/)

##Summary
ScrollMagic is a ___ jQuery plugin which turns your insane (yes, they're insane) ideas into fun, interactive, and engaging experiences for your users! It is a collection of intuitive UI design patterns that you can incorporate into your prospective web applications. It takes an object oriented approach using a controller for each scroll container and attaching multiple scenes which define when which events should fire.

##Installation

There are a couple of ways of installing ScrollMagic. The options include:

**Github**
`git clone git://github.com/janpaepke/ScrollMagic.git`

**NPM**
`npm install scrollmagic`

**Bower**
`bower install scrollmagic`

**CDN**
`http://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.5/ScrollMagic.min.js`

##Usage

ScrollMagic makes it really easy to trigger animations based on scroll positions (Magic is in the friggin name)! Below is a simple example of implementing custom classes based on scroll position:

```js
// init controller
var controller = new ScrollMagic.Controller({globalSceneOptions: {duration: 100}});

// build scenes
new ScrollMagic.Scene({triggerElement: "#sec1"})
  .setClassToggle("#high1", "active") // add class toggle
  .addIndicators() // add indicators (requires plugin)
  .addTo(controller);

new ScrollMagic.Scene({triggerElement: "#sec2"})
  .setClassToggle("#high2", "active") // add class toggle
  .addIndicators() // add indicators (requires plugin)
  .addTo(controller);

new ScrollMagic.Scene({triggerElement: "#sec3"})
  .setClassToggle("#high3", "active") // add class toggle
  .addIndicators() // add indicators (requires plugin)
  .addTo(controller);

new ScrollMagic.Scene({triggerElement: "#sec4"})
  .setClassToggle("#high4", "active") // add class toggle
  .addIndicators() // add indicators (requires plugin)
  .addTo(controller);
```
---

ScrollMagic is also compatible with [GSAP](https://greensock.com/gsap) (GreenSock Animation Platform) and [VelocityJS](http://velocityjs.org/) and leverages these animation plugins to create their animations. It also includes callback-based functions which allow for greater flexibility in the way you want your app to respond to scroll events.

An advanced implementation of ScrollMagic's libray with the use of GSAP is creating section slides:

---
```js
$(function () { // wait for document ready
// init
var controller = new ScrollMagic.Controller();

// define movement of panels
var wipeAnimation = new TimelineMax()
	// animate to second panel
	.to("#slideContainer", 0.5, {z: -150})		// move back in 3D space
	.to("#slideContainer", 1,   {x: "-25%"})	// move in to first panel
	.to("#slideContainer", 0.5, {z: 0})				// move back to origin in 3D space
	// animate to third panel
	.to("#slideContainer", 0.5, {z: -150, delay: 1})
	.to("#slideContainer", 1,   {x: "-50%"})
	.to("#slideContainer", 0.5, {z: 0})
	// animate to forth panel
	.to("#slideContainer", 0.5, {z: -150, delay: 1})
	.to("#slideContainer", 1,   {x: "-75%"})
	.to("#slideContainer", 0.5, {z: 0});

// create scene to pin and link animation
new ScrollMagic.Scene({
		triggerElement: "#pinContainer",
		triggerHook: "onLeave",
		duration: "500%"
	})
	.setPin("#pinContainer")
	.setTween(wipeAnimation)
	.addIndicators() // add indicators (requires plugin)
	.addTo(controller);
});
```

##Resouces

Below are a couple resources that would be excellent to reference in your future ***Magical*** projects.

---

[ScrollMagic Docs](http://scrollmagic.io/docs/index.html)

[GreenSock](https://greensock.com/gsap)

[VelocityJS](http://velocityjs.org/)

##Support
ScrollMagic aims to support all major browsers in recent versions:
**Firefox 26+, Chrome 30+, Safari 5.1+, Opera 10+, IE 9+**

It has over 8,000 stars and 1,300 forks on Github

##License
ScrollMagic is dual licensed under the MIT license and GPL.
For more information click [here](https://github.com/janpaepke/ScrollMagic/blob/master/LICENSE.md).
