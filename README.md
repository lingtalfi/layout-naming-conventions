Layout naming conventions
===========================
2017-04-06 --> 2017-05-06



Layout naming conventions for themable applications.




Intro
==========


What's a themable application?

An application in which you can change the theme.
So, your website has a certain look'n'feel, using theme A.

Then you switch to theme B (by clicking a button for instance),
which effectively changes the look'n'feel of your website.



The goal of layout naming conventions is to be able to RE-USE layouts from one theme to another.



Assuming that every "interesting" element on the page is a widget, if you look at a website page and try to name every 
widget on the page, you will probably end up with a lots of widgets.
 
Trying to organize them in layouts can then be a very tedious task, as there are plenty of possible combinations.

For instance, look at this home page of a quite popular website in France, and try to name widgets.


[![boulanger.jpg](https://s19.postimg.org/xvy02s1nn/boulanger.jpg)](https://postimg.org/image/qsq4n5w7z/)









Here is a possible attempt I made.
To do so, I was only using the widget ids and position names (from the [laws](https://github.com/lingtalfi/laws) system),
asking myself: is that a widget or a position?

It turns out my mind was oriented to the old Joomla way of doing things (I don't know if this has changed since
the last time I checked many years ago), which basically was: everything is a position.
 
But re-analyzing the page with the possibility of using a simple widget instead of a position seems more adapted to me.

For instance, think of the search bar, that's a widget that a lot of websites have.
Do you need a position for that, or just the widget?

A position helps you grouping widgets together, but in the case of a search bar, you know that there is only
one widget, and therefore, perhaps surprisingly, using a widget alone might be a more optimized choice.   



- 1
    - widget id: toplinks
    - widget name: LinksWithIconsBanner
- 2
    - widget id: logo
    - widget name: Logo
- 3
    - widget id: search
    - widget name: Search
- 4
    - position name: actionbar
        - widgets:
            - 0: 
                - widget id: actionbar_my_account
                - widget name: LinkWithIcon
            - 1: 
                - widget id: actionbar_my_cart
                - widget name: CartIcon
- 5
    - widget id: topmenu
    - widget name: HorizontalMenu
- 6
    - position name: maincolumn
        - widgets:
            - 6:
                - widget id: slider
                - widget name: Slider
            - 7: 
                - widget id: featured_products
                - widget name: FeaturedProducts
            - 8:                
                - widget id: banner-1
                - widget name: LinkBanner
            - 9:                
                - widget id: banner-2
                - widget name: TextBanner
            - 10:                
                - widget id: banner-3
                - widget name: PhotoBanner
            - 11:                
                - widget id: banner-4
                - widget name: LinkBanner
            - 12:                
                - widget id: banner-5
                - widget name: DualLinkBanner
            - 13:                
                - widget id: banner-6
                - widget name: LinkBanner
            - 14:                
                - widget id: banner-7
                - widget name: DualLinkBanner
            - 15:                
                - widget id: partners
                - widget name: Partners
            - 16:                
                - widget id: category_links
                - widget name: FlatMenu
            - 17:                
                - widget id: promo_text
                - widget name: PromoText
            - 18:                
                - widget id: promo_links
                - widget name: PromoLinks
- 19:
    - widget id: our_brand
    - widget name: LinksWithIconsBanner
- 20 (left):
    - widget id: social_links
    - widget name: SocialLinks
- 20 (right):
    - position name: more_services
        - widgets:
            - 20: 
                - widget id: subscribe_newsletter_link
                - widget name: LinkWithIcon
            - 20: 
                - widget id: download_app_link
                - widget name: LinkWithIcon
              
- 21:
    - position name: footer
        - widgets:
            - 0: 
                - widget id: find_our_store 
                - widget name: FindOurStoreInsert
            - 1: 
                - widget id: footer_links 
                - widget name: FlatMenu
            
            
            
            
            
            
            
            
But then, I thought that trying to standardize layouts with this way of naming things would be a nightmare,
there had to be a better solution.

So I went to another page, and then it appeared clear to me that some parts of the website are simply re-used
from one page to another.

If you look at the following page (from the same french website), you will see that there is a top part
and a bottom part that is the same as the previous page.


[![boulanger-search.jpg](https://s19.postimg.org/j19eols2r/boulanger-search.jpg)](https://postimg.org/image/efdag96jj/)



So, then it appeared clear to me that I was missing this part of the puzzle: the includes part.
Since then, "includes" is now part of the laws framework.

Includes work like an include in php.
This is perhaps the most powerful tool as far as creating templates is concerned.

With includes, we can easily achieve the original goal of classifying layouts.

The tendency nowadays (2017) for website layouts is a top, a middle, and a bottom.

I call that a sandwich layout, and that would be the first layout in lnc1.







LNC_1
=============


[![lnc1.jpg](https://s19.postimg.org/6358cxkv7/lnc1.jpg)](https://postimg.org/image/vlxkpy4f3/)


So far, LNC1 identifies three categories of layouts:


- sandwich layouts
- splash layouts
- admin layouts



sandwich layout
-------------

This is a very common layout for websites.
It has a top and a bottom part that remains the same across all the pages of the website.
Then the middle part can be either one, two or three columns.

The top and bottom parts are constant: their code won't change from page to page.
But the middle part varies from page to page, and therefore is delegated to positions (so that the theme integrator
can bound the desired widgets to them, depending on the page).



splash layout
-------------
Some pages of the website don't keep that identity that the sandwich layout conveys across all pages.
Some pages are just one big screen with only one element of focus on it.

For instance, imagine an admin login screen with only one login form in the middle.
Depending on your business decisions, you could use a splash layout for pages like maintenance page, 404 page,
403 page, error page, exception page, admin login page, and maybe other pages.



admin layout
-------------
This is a common layout for admins.
It's basically like the sandwich layout 1 column, but with a side bar inclusion on the side (usually left).


ajax layout
-------------
This is the simplest layout, it basically only displays a "main" position.
It's like the splash layout, except that often the splash layout contains itself some html, while the ajax layout doesn't.

















