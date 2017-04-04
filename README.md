Layout naming conventions
===========================
2017-04-04



Layout naming conventions for themable applications.




This document only describes conventions (no code).





Why?
==========

If you use a themable application, like for instance one using the [laws](https://github.com/lingtalfi/laws) system,
you will need to create some layouts and some widgets.

As your application is probably modular, those layouts/widgets will probably be brought by module authors, layout authors,
or widget authors.

When a module author wants to create a page in your application, at some point she will need to choose a layout name.
Also, that layout contains positions (in a system like laws), and those position names also need to be chosen.
 
The natural thing that would happen is that module authors will name their layouts/positions using their common sense.


So imagine we have two modules authors: paul and alice.

Paul will create a module that brings a maintenance page to the application.
Alice will create a module that brings a 404 error page to the application.


So paul creates his files, and his structure looks like this:

```txt
- app
----- theme
--------- default_theme
------------- layouts
----------------- maintenance/default.tpl.php
------------- widgets
----------------- maintenance/default.tpl.php
```

Then alice creates her files, and her structure looks like this:

```txt
- app
----- theme
--------- default_theme
------------- layouts
----------------- 404/default.tpl.php
------------- widgets
----------------- 404/default.tpl.php
```

So, if you merge paul and alice's work together, you obtain this structure:

```txt
- app
----- theme
--------- default_theme
------------- layouts
----------------- maintenance/default.tpl.php
----------------- 404/default.tpl.php
------------- widgets
----------------- maintenance/default.tpl.php
----------------- 404/default.tpl.php
```

So, basically two different layouts and two different widgets.
That seems reasonable.

However, if you think about it both maintenance layout and 404 page layout have something in common:
they only expose ONE widget.


Imagine we told alice and paul that for a page containing only one widget, 
the layout shall be named "landpage".

Then, for the same exercise, we would have ended up with the following structure:
 
```txt
- app
----- theme
--------- default_theme
------------- layouts
----------------- landpage/default.tpl.php
------------- widgets
----------------- maintenance/default.tpl.php
----------------- 404/default.tpl.php
``` 

So, in this case, one layout and two widgets.

Why does that matter?
Imagine we want to create a new theme.
So, instead of theme A, we switch to theme B.

So now, all those layouts need to be duplicated.
And every time we change the theme, another copy will be created.
It's easy to understand that the more files you have in a theme, the more time you will spend on it,
and so the fewer files the better.

Plus, layouts use positions, if we also told paul and alice that a "landpage" layout only uses ONE position
named "main", then you can imagine how that would save everybody some work at the end of the chain.


So, the goal of this page is to define some naming conventions for layouts, so that module authors can
refer to them, and name their layouts after them, and so that in the end less work has to be done
when a theme needs to be created.


Hopefully that makes sense.








LNC_1
=============


WORK IN PROGRESS.
Layout naming convention 1.


The following layouts/positions are available:

- landpage
    - main


landpage
-------------
The landpage is a layout which contains only one widget.
One should use this layout when the web user ends its journey.

Examples: maintenance page, 404 page, 403 page, error page, exception page, 
splash? login page (a login page containing only one big login form in the center).


















