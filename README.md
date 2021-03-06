# MobileMenu.js

The Mobile Menu plugin scans an existing multi-level navigation menu and dynamically builds a dropdown list which 
navigates the user to the selected page on the select elements change event. It is true that there are a few other 
plugins out there that do this already, however most of them don’t seem to handle a menu that is more than 1 level deep.

These are the steps to get it working:

1) Make sure your navigation menu is in the format:

```html
<nav>
	<ul>
		<li><a href="/">Home</a></li>
		<li><a href="/services/">Services</a>
		<ul>
			<li><a href="/services/web-development/">Web Development</a></li>
			<li><a href="/services/online-marketing/">Online Marketing</a></li>
		</ul>
		</li>
		<li><a href="/contact-us/">Contact Us</a></li>
	</ul>
</nav>
```

2) Add the following scripts to your website:

```html
<script src="/js/jquery.js"></script>
<script src="/js/jquery-mobilemenu.js"></script>
```

3) Invoke the mobileMenu function on the empty dropdown list you wish to have populated:

```html
<script>
jQuery(document).ready(function($) {
	// build select menu (for mobile) from main nav
    	$("nav > ul").after("<select id='ddlMobileNav'></select>");
    	$("#ddlMobileNav").mobileMenu({ ulsource: "nav > ul", maxlevel: 2 });
});
</script>
```
The parameters you can specify for the mobileMenu function are:
ulsource: The jquery selector referencing your unordered list.
maxlevel: The maximum number of levels of the main navigation you wish to traverse.


You should now have a dropdown menu that will navigate the user to the selected page. 


Media Queries
-------------
And finally, don’t forget to use media queries to hide the main navigation when the screen size is below a certain width, and likewise to hide the select menu when the screen width is larger than mobile.

