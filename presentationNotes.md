# todo today

- read it

# Using animation to orient and give context

- Animation can help orient users to the spatial relationships in your interface.

## Create a mental model of what's out of view

- It's impossible to fit large amount of content into small amount of space
- thus emerged: off-screen nav that exist in layers stacked in front of view
- using animation to transition layers into view helps reinforce spatial relationships
- [click Wacom] - here is an example of using motion to orient users to the layers of an interface
- hovering over one of the menu items reveals submenus
- notice the main nav shrinks giving visual hint that subnav is a layer behind it
- imagine if animation were removed -- jump-cut, context-shift is confusing

## Orient interface layers with animation

- [click Shopify] - here is an example of a layered technique that splits the interface due to different contexts
- when modal is opened, it animates toward viewer, indicating a move to a higher layer that exists above current page

## Orient user to off-screen objects

- [click Cotton Bureau] - off-screen patterns have become more common as screens have gotten smaller
- both nav and shopping cart are off-screen elements that transition into view
- reinforces the mental model that the content is waiting in the wings

## Guide tasks

- [click readme] - can help guide users through linear task flows
- at first glance, it's just an illustration, but as you fill out the form it follows you
- this animation both guides the task and to convey brand personality

## Inform context changes

- [click codepen] - a change in context of the content itself (like switching to a detailed view)
- or a change of the interaction mode (like switching from input mode to editing)
- animation can help reduce potential confusion in both cases above by connecting content through context changes

# Using animation to direct focus / attention

## Display most important content

- [click fitbit] - dashboard totals and badges to celebrate hitting a goal are the only things that animate

## Direct eye with motion

- [click codepensave] - reminds users "don't lose your work"
- uses exaggeration motion to match the importance of the task

## hold attention with visual eye flow

- A logical flow of motion can make following the flow of info feel almost effortless
- vs. motion that seems to come and go from all directions causes tension
- visual continuity means letting an element continue to be itself throughout a transition
- [click twitter] - here the avatar stays on-screen when you're moving from list view to detail view
- benefits: the fact that it stays on-screen makes it easy to remember which selection was made.

# Using animation to show cause and effect

- useful for confirming the effect of an action that a user has taken

## guide tasks by hinting at affordances

- affordance is the concept of possibility of an action that can be taken with an object (anticipation)
  [click clear app] - as you move mouse to bottom of list, a new blank list rotates slightly downward hinting that a new list can be created

## Cue by exposing additional actions

- reveal info relevant to the immediate task at hand just as it's needed so as to avoid overwhleming your users with options
- [click dropbox] - each icon bounces in offering options and assistance

## Cue the onboarding process

- [click slack] - When someone is completely new to your app they could use some help discovering how to use it
- Slack uses animated icons to reveal different features
- low-key enough to be ignored so new users aren't forced into interacting with the tips

## Preview the effect of an action

- cause and effect can be used to anticipate reordering content
- [click Docs] - you see the docs you're sorting move into a neat pile under your cursor
- a number marker indicates how many files you're moving

# Using animation for feedback

- Animation can help make feedback better

## Animate effective error msgs

- Animating effective and attention-grabbing error messages
- [click Stripe] - The shaking animation is paried with a red outline around the problematic fields, almost like the form is shaking its head at you

## Visually confirm tasks without losing your place

- [click slides] - the save button animates from disk, to spinner, to checkmark
- indicating along the way that your data is being saved, behind the scenes, all within a very compact space

## Loader animations that convey progress

[click Surepayroll] - you maynot know how long a loading operation will take

- a custom loader can create added trust because it's not the same generic spinner you see
- users are more willing to wait for custom loading animations than generic ones
- wait times seem to go by more quickly

# fadein fadeout

- This is to let you know that this is available in jQuery
- so if you're in a work environment where you have jQuery and you don't want to use native JS, but you want to do something simple, this is for you
- Here is the syntax: using jQuery - get the DOM element, say what effect you want -- .fadeOut, and put the number of ms
- Similarly if you want to fadeIn you use .fadeIn
- So here is my green box where if I click it, it will use jQuery to fadeOut
- Now notice the behaviour of what just happened? -- everything went down
- Q: Why do you think that is?
- A: as it's fading out the opacity is going away, the DOM element is still there taking up space, and then at the end, it says 'display:none'
- when it's display: none, the DOM element is no longer there taking up space which is why the rest of the HTML moves down
- GO INTO the codepen and we're going to try it out and you're going to submit this for your in-class exercise
- notice we've included jQuery

```js
const duration = duration;

// STEP 1: Create document ready event handler
$(document).ready(function() {
  // STEP 2a: Create onclick handler for <button id="out">Fade Out</button>
  $("#out").click(function() {
    // STEP 2b: In 3s, fade out <h2 class="fade">Fade Out / Fade In</h2>
    $(".fade").fadeOut(duration);
  });

  // STEP 2c: Create onclick handler for <button id="in">Fade In</button>
  $("#in").click(function() {
    // STEP 2d: In 3s, fade in h2 element
    $(".fade").fadeIn(duration);
  });
```

# slideUp slideDown

- read it
- Here is the syntax, very similar to the fadeIn - you just use slideUp and slideDown
- slides in jQuery might be counter-intuitive depending on your css (display: inline-block vs block)
- I'm going to click on this green square
- Inspect the code behind that to see --- slideUp

```js
// STEP 3a: Create onclick handler for <button id="down">Slide Down</button>
$("#up").click(function() {
  // STEP 3b: Slide down <h2 class="slide">Slide Up / Slide Down</h2>.
  $(".slide").slideUp(duration);
});

// STEP 3c: Create onclick handler for <button id="up">Slide Up</button>
$("#down").click(function() {
  // STEP 3d: Slide back down the h2 element
  $(".slide").slideDown(duration);
});
```

# passing ms

- instead of milliseconds, you can also pass these keywords - slow, normal, fast
- I've actually coded that in - so you can see what that looks like
- demo it by clicking on slow, normal, fast

# .hide .show

- read it
- click green square and it both fades out and slides
- try it on codepen
- so far we've used classes and ids to target stuff in jQuery; fyi - you can also target using .prev()
- so for this I purposely didn't give you an easy id or class to grab, just to make you aware that jQuery can do .prev()
- big takeaway: besides the .hide you can navigate the DOM if you need to

```js
// STEP 4a: Create onclick handler for hide
$("#hide").click(function() {
  // STEP 4b: Hide H2 element
  $(this)
    .prev()
    .hide(duration);
});

// STEP 4c: Create onclick handler for show
$("#show").click(function() {
  // STEP 4d: Show all elements that have the hidden style class
  $(this)
    .prev()
    .prev()
    .show(duration);
});
```

# .toggle

- read it
- click green square
- Q: How many jQuery effects are being used here?

```js
  // STEP 5a: Create onclick handler
  $("#toggle").click(function() {
    // STEP 5b: Toggle the H2 element
    $("#tog").toggle("slow");
```

# .slideToggle .fadeToggle

- read it
- click the green and purple squares

```js
    // STEP 5c: Toggle fade or slide the H2 element just before button
    // $('#tog').fadeToggle();

    // $('#tog').slideToggle();
  });
```

# .stop :animated

- so you can filter for all things that are currently animating and you can stop it via the .stop() method
- read it
- click the square then the button

```js
  // STEP 6: Create a new button to be added to the DOM that stops all animations in progress
  $("#stop").click(function() {
    $("body *")
      .filter(":animated")
      .stop();
  });
});
```

# Doing something

- You can do something after an animation completes
- read it
- so in this example, they're assuming the addClass will happen after the fadeIn but that's a common mistake
- so this is not quite right; you don't want to do that
- rather - read it
- so here's the fadeIn method where you have the duration as usual, but the second parameter is your callback
- that's just an fyi if you need it

# Jeopardy codepen

```js
const duration = 600;

$(document).ready(function() {
  // jQuery $100 - fadeOut / show
  $("#jq .q100").click(function() {
    $("#jq .q100 h2").fadeOut(duration, function() {
      $("#jq .q100 p").show();
    });
  });

  // jQuery $200 - slideUp / slideDown
  $("#jq .q200").click(function() {
    $("#jq .q200 h2").slideUp(600, function() {
      $("#jq .q200 p").slideDown(600);
    });
  });

  // jQuery $300 - toggle
  $("#jq .q300").click(function() {
    $("#jq .q300 h2").toggle(duration);
    $("#jq .q300 p").toggle(duration);
  });

  // jQuery $400 - fadeToggle
  $("#jq .q400").click(function() {
    $("#jq .q400 h2").fadeToggle(duration, function() {
      $("#jq .q400 p").fadeToggle(duration);
    });
  });

  // jQuery $500 - slideToggle
  $("#jq .q500").click(function() {
    $("#jq .q500 h2").slideToggle(duration, function() {
      $("#jq .q500 p").slideToggle(duration);
    });
  });
});
```

# .animate()

- Here's the syntax .animate
- you put in whatever properties you want in curly braces because it's an object
- also you have the option to put in duration
- read it
- so if you try animating to backgroundColor: yellow -- it won't work
- I'm using position: relative on the parent, and position: absolute for the ball
- so if I click on Run, you should see code in action
- Q: what do you predict will happen? It will move 100px to right or left?
- Because I have the plus sign here, if I click it again, it keeps on going (it remembers it's last state)
- If I had just said '100', then it would have moved once and that's it because it's already at 100px
- 1000 refers to ms
- Keep clicking
- so that's the basic use of .animate()

# .animate easing

- in addition to the duration, you can optionally put in the easing
- read it
- so by default it uses swing, so let's try using the other one -- linear and compare it to what we saw before
- play the one before, play the one now
- important to make sound effects

# Easing plugins

- so let's try to use these plugins
- introducing the jQuery UI library (click link)
- this is separate thing from jQuery, so in order to use this you need both jQuery, and jQuery UI
- once you've downloaded it, you can then use this method called .effect() - click link 'effect'
- so here is a dropdown menu of other easings you can try
- let's try bounce, explode, shake etc
- so let's try it
- so in my green circle, all I said was .effect('bounce') - this word 'bounce' I just chose it from one of these words in dropdown menu
- click run
- now one thing I did notice was if you had .animate followed by .effect, what happened was this
- click other run
- but what if your intention was to bounce along as it moved along
- you can do that, but not with jQuery UI but rather Robert Penner's famous jQuery easing plugin

# Penner's plugin

- click link 'library'
- apparently this guy was famous back in the day because he created this easing plugin
- and here are some examples of his work
- on the left hand side, this dropdown menu refers to the easing as it begins to animate = easeOutElastic
- on the right hand side, this dropdown menu refers to the easing as animation ends = easeOutBounce
- note: last update was 2007 - that's how old this is
- and he did this using just pure mathematics
- Actually go to that CDN link to view equations
- So I've already included that library
- You don't use it with .effect (because .effect is with jQuery UI library)
- Rather you use it within the .animate() method
- so instead of saying 'linear', you can say whatever you wanted as listed in Penner's dropdown menu
- again this was back in the day when jQuery was dominant, so this was eye-opening for a lot of people

# .animate callbacks

- And you can also have callbacks
- so once the animation is done, you can do something else

# Frogger codepen

```css
/* STEP 2 - create keyframe hopup that makes frog slender */
.hop-up {
  animation: hopup 0.15s;
}
/* STEP 3 - create .hop-up class that uses your animation keyframe hopup */
@keyframes hopup {
  50% {
    transform: scale(0.8, 1.3);
  }
}
```

```js
const audio = document.querySelector("audio#hop");
const music = document.querySelector("audio#music");

function playHop() {
  audio.currentTime = 0;
  audio.play();
  music.isPlaying ? null : music.play();
}

function moveUp() {
  // STEP 1 - Make frog move up 37px. (check position prop in CSS)
  // STEP 4 - make frog slender as it hops (via adding a class that uses keyframes but removed thereafter)
  $("#frog")
    .stop()
    .addClass("hop-up")
    .animate({ top: "-=37" }, 150, () => {
      $("#frog").removeClass("hop-up");
    });
}

$(document).ready(function() {
  music.volume = 0.1;

  $(window).keydown(function(e) {
    playHop();

    switch (e.key) {
      case "ArrowUp":
        moveUp();
        break;
      default:
        console.error("direction incorrect");
    }
  });
});
```

# Lab 6 jQuery Animation side nav with arrow

- the main goal is to make this side menu bounce open and have the arrow turn around
- notice the nav element has a class of slideOut which will be useful later on
- notice header nav.slideOut:hover - using CSS alone by hovering over the nav it moves over 100px
- code it
- 1st step is including appropriate libraries, jquery, jqueryUI, Penner's easing

## Step 5

- let's begin there - you want to disable the hover functionality by removing the slideOut class on the nav via JS
- good for progressive enhancement, so even if no JS, it still works
- Q: so how would you do that in jQuery? A: removeclass
- `$("nav").removeClass("slideOut");`

## Step 6

- we're going to declare a variable to keep track of whether of not the nav is open or closed

## Step 7

- Q: what element is the arrow? A: this anchor tag; Q: How do you want to target that?
- `$("nav > a").click(function(e) {`
- for now just put an alert to see if it's working

## Step 8

- normally when you click a link, the browser wants to go somewhere; to prevent that from happening you use
- `e.preventDefault();`

# Step pre-9

- could say `if (is_navOpen === false)`
- or a better way to say that `if (!is_navOpen)`

# Step 9

- Q: How are you going to slide it open? A: we can animate that nav to move right
- `$('nav').animate({ left: '-100px'}, 300);`
- let's experiment and see what happens if we say 0px, then try 400px
- we've taken care of the nav opening which is great. Next is we want it to bounce as it opens, which involves the easing
- since we've included Penner's easing library, we can say:
- `$('nav').animate({ left: '-100px'}, 300, "easeOutElastic");`

# Step 10

- I want arrow to rotate 180deg once it finishes expanding
- Notice we already have a class called .rotated; so once I add that class to this arrow, it should turn around
- Experiment by manually putting that class in anchor tag to see if arrow turns; it does
- So let's programmatically add that in AFTER that animation is done -- which means we're dealing with a callback

```js
$("nav").animate({ left: "-100px" }, 300, "easeOutElastic", function() {
  // STEP 10: Add class to arrow once nav is done animating
  $("nav > a").addClass("rotated");
});
```

- Notice, there exists a transition statement already in CSS which should make the animation smooth
- hmm, it's too quick, change .2s to 1s to exaggerate it

# Step 11

- is already done

# Step 12

- so far, open works, but does close work? No
- so here we can continue the above if() structure

```js
} else {
  $('nav').animate({ left: "100px" }, 300, "easeOutElastic"
}

```

# Step 13

- so far it doesn't work due to logic error
- but in reality, the variable never changed, it's still false
- so you could do this in one of 2 ways, either say in the if() section `is_navOpen = true`, else section `is_navOpen = false`
- OR can say at bottom `is_navOpen = !is_navOpen;`

# Step 14

- last thing to do is make that arrow turn around
- so we're going to do the same kind of thing where we'll need a callback

```js
.animate({ left: "-100px" }, 300, "easeOutElastic", function() {
          // STEP 10: Add class to arrow once nav is done animating
          $("nav a").removeClass("rotated");
        });
```

```js
// STEP 4: Create document ready event handler
$(document).ready(function() {
  // STEP 5: Disable CSS interaction (see CSS above)
  $("nav").removeClass("slideOut");
  // STEP 6: Set variable to track state of nav panel
  let is_navOpen = false;
  // STEP 7: Build onclick handler, with if/else for open/shut
  $("nav > a").click(function(e) {
    // STEP 8: Disable default behaviour for hyperlink
    e.preventDefault();
    // STEP pre-9: decide if open or closed
    if (!is_navOpen) {
      // STEP 9: Slide open the nav element.
      // How? .animate? .stop? Why -100? easeOutElastic? is_navOpen?
      $(this)
        .parent()
        .animate({ left: "-100px" }, 300, "easeOutElastic", function() {
          // STEP 10: Add class to arrow once nav is done animating
          $("nav a").addClass("rotated");
        });

      // STEP 11: Go to CSS section and add class rotated that handles transform.  Add transition to appropriate place.
    } else {
      // STEP 12: Do reverse and slide shut the nav element. no callback?
      $(this)
        .parent()
        .animate({ left: "-300px" }, 300, "easeOutElastic");
      $("nav a").removeClass("rotated");
    }
    // STEP 13: Set state/flag to opposite boolean value
    is_navOpen = !is_navOpen;
  });
});
```
