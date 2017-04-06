Boulanger
=============
2017-04-05




============
Todo:
group 1-5 is header,
it should be only one widget called header,
which internally calls all widgets 1-5.

Idem for footer.

If you can't, then you need another mechanism any way to be able to re-use parts
of the design from page to page.
============






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
            
            
            
            
            