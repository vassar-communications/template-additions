

<!-- 
	
	NOTE: this document is probably a lot easier to read if you're looking at the
	rendered version in the repo.
		
-->

# The basic idea

This is intended to be a design system, to be managed and expanded over time. With that in mind, I've structured this in a way that I think is sustainable and extensible.

This, of course, is just a start. I've organized this system in a way that makes sense to me personally, but I haven't been working with it that long, and I won't be the only one working with it.


One thing: In my own projects, I normally keep typography, visual styling/color, and layouts strictly separate. The idea is that a module - a blog post, search box, etc - should be generic enough to be transplanted into a different project without having to strip out a lot of visual or typographic styling. I originally following that thinking here. However, having three different buckets for each item—dividing a module's styling into three different areas—does make it a little harder to edit something. In this case, I don't see us trying to re-use a module for a completely different site design, and I think the overhead of trying to keep everything generic might not be worth the convenience of being able to quickly repurpose a module. Again, time will tell if this is the right way to do things, but for now, I've been storing all styling in each module's file.


Organizational structure is as follows.

# Structure

## Tools

This contains supporting code that the rest of the site styling may depend on: mixins, utility libraries, etc.


## Basics

The Basics folder contains sitewide, generally applicable styling. Examples of this would be reset styling, styling to set all images to 100%, border-box overrides, that kind of thing. It's pretty empty right now because a lot of what would be in here is provided by the central template styling that this repo currently sits on top of.


## Typography

This contains the basic typographic styles used by all other modules. There's no reason to keep rewriting the code for a small sans-serif, or a large serif header; there's only a limited range of typographic styling used by this system. Rather than having the same CSS code written over and over again in each module, I'm defining those styles once and centrally, and invoking them in modules as needed. Here's how that works.

### _styles.scss

This contains a nested SASS map of all typographic styling. A map is SASS's way of storing key-value pairs. In this instance, each category of style - serif, sans-serif - has its own map, and that map contains a map for 


Initially I was using regular variables to store shorthand declarations, as follows:

`$sans-serif-small: normal 1em/1.2 Source Sans, sans-serif;`

There were a few problems though:

- Font shorthand properties don't contain things like letter-spacing or text-transform. Either this would have to be added via an override, or some font styles would require their own mixins.

- Most if not all of the elements will need different type styling—typically font-size and line-height—at different breakpoints, and variables can't include breakpoints. You'd have to either have different variables for each breakpoint, and write the breakpoints yourself, or again, have a single mixin that handles the different states.

I did some experimenting, and kept coming back to the same conclusion: if we wanted to have a library of re-usable typographic styles, variables weren't sufficient—we'd need a mixin-based solution.

So I came up with a series of mixins for each style, but that rapidly got clunky. Worse, some of the different styles were very similar: small sans-serif and small sans-serif condensed are the same, the only difference being the line-height. The approach I ultimately settled on was storing these styles in a map, and accessing them via a single mixin as follows:

```
p {
	@include font(sansSerif, small);
}
```

Advantages:

- You can see at a glance all the different styles for serif, sans, etc

- Styles can be mixed and matched. 

- If we ever decide to generate 



## Components






Helpers
-------

Helpers are utility classes that modify an element's behavior or appearance: things like changing width, padding, or visibility.



Atoms
-----

Atoms are small, generic, single-purpose elements like buttons.


Modules
-------

A module is a 


Layouts
-------

Layouts are generic structures that wouldn't typically have any visual styling on their own; they exist only to contain modules. An example would be the media object, or a grid system.


Templates
---------







# Guidelines

## Margins

In some circumstances, I'm avoiding shorthand for margins:













































