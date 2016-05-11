# Social Nav Bar Code Along Code Along

## Objectives

1. Review Sprite Images
2. Review CSS Rollovers

## Introduction

Building upon previous code alongs, in this exercise you will add rollover icons to the social media navigation on each page by coding along with the video provided. This will help you to review the concepts you were introduced to in the previous lessons.

## Instructions

1. Fork this repository.
2. Use Terminal to clone your forked copy.
3. Then change directory into the repository folder.
4. Code along with the provided video below and/or its supplementary reading located below the video. Code everything you see there. Feel free to stop, pause, rewind or fast forward through the content to keep pace.

<iframe width="100%" height="720" src="//www.youtube.com/embed/DjAGtFUbmYg?rel=0&controls=1&showinfo=1" frameborder="0" allowfullscreen></iframe>

### Building A Social Nav Bar

Lets start out by making a new feature branch in Terminal by typing `git checkout -b social-icons` and press return. 

Next, open the index.html page in your code editor. Let's add some new class names to our links in the `<div id="social">` element.

```html
<div id="social">
  <a class="twit" href="#" title="Twitter">Twitter</a>
  <a class="fbook" href="#" title="Facebook">Facebook</a>
  <a class="gplus" href="#" title="Google Plus">Google Plus</a>
</div>
```

Save the index page, then open the style.css file in your code editor. Then scroll down to the comment in the code labeled "SOCIAL" and update the following code. 

```css
/*////////// SOCIAL //////////*/

#social {
  position: fixed;
  top: 185px;
  right: 20px;
  width: 40px;
  z-index: 2;
}

#social a {
  display: block;
  width: 40px;
  height: 40px;
  text-indent: 100%;
  white-space: no-wrap;
  overflow: hidden;
}

a.fbook, a.twit, a.gplus {
  background: url(../images/social-icons.png) no-repeat;
}
```

We removed the yellow background color we had added in the orevious code along. Also on line 8 in the code snippet above we updated the z-index to 2 to match the z-index of the fixed navbar we adjusted in the previous code along. Then on the links we set `text-indent: 100%;` on line 15 to push the text inside of the social links outside of its width. Then on line 16 we added `white-space: no-wrap;` to prevent the text from wrapping inside the element, and on line 17 we added `overflow hidden;` so the text indented outside the element would not appear. All of these wrok together to hide the text inside the links. Why do this? Well, the text is helpful for search engines. Although we do not really need our site visitors to see the text becuasethey will be seeing icons instead.

Now we need to add hover state and active states for each icon to reposition the background image one hover and click like so:

```css
/*////////// SOCIAL //////////*/

#social {
  position: fixed;
  top: 185px;
  right: 20px;
  width: 40px;
  z-index: 2;
}

#social a {
  display: block;
  width: 40px;
  height: 40px;
  text-indent: 100%;
  white-space: no-wrap;
  overflow: hidden;
}

a.fbook, a.twit, a.gplus {
  background: url(../images/social-icons.png) no-repeat;
}

a.fbook { background-position: 0 0; }
a.fbook:hover { background-position: -40px 0; }
a.fbook:active { background-position: -80px 0; }

a.twit { background-position: 0 -40px; }
a.twit:hover { background-position: -40px -40px; }
a.twit:active { background-position: -80px -40px; }

a.gplus { background-position: 0 -80px; }
a.gplus:hover { background-position: -40px -80px; }
a.gplus:active { background-position: -80px -80px; }
```

For background-position remember the first value is the horizontal positioning and the second value is the vertical positioning. We cange the numbers to reposition the image during different link states. For more details on this refer back to the previous lecture video on image sprites and rollovers.

Save the CSS page and refresh in the browser and you should have functional social icons. Hurray!

It's now time to version our changes using Git. To do so, in Terminal type `git add .` and press return. Then type `git commit -m "finish social icons"` and press return. Then push up this feature branch `git push -u origin social-icons` and press return. Next merge the changes into your master branch. Type `git checkout master` and press return, then `git merge social-icons` and press return. Then `git push origin master` and press return.

After you finish, make sure you install Firefox if you haven't already as it is required for the screenshot tests to run. Then, type learn command from Terminal to run local tests (Mac) or type learn-test for Windows.

After all tests are passing submit a pull request on Github and move on to the next lesson!

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-code-along-ex-6' title='Social Nav Bar Code Along Code Along'>Social Nav Bar Code Along Code Along</a> on Learn.co and start learning to code for free.</p>

<p class='util--hide'>View <a href='https://learn.co/lessons/fe-code-along-ex-6'>Social Nav Bar Code Along</a> on Learn.co and start learning to code for free.</p>
