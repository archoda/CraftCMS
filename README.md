### Local Installation & Set-up

1. Manual Download of Craft CMS for OSX
    - OR - COPY CMS FILES and EXPORT SQL ( https://craftcms.com/knowledge-base/duplicating-a-craft-site)
2. Create Website URL / LocalHost (MAMP)=
    - ENSURE PHP < 8 TO NOT REQUIRE GD/ImageMagic
    - https://samsonasik.wordpress.com/2021/01/04/install-imagick-extension-for-php8-in-macos-big-sur/
    - Update PHP.ini max_execution_time to 120 and memory_limit to 256M
3. Copy/Paste CraftCMS to Localhost -> web directory
4. Create MySQL database + privileges ( IMPORTANT: collate as utf8_unicode_ci )
5. Update .env file for Driver, Server, MySQL/Port, DB Name, User, Password, Prefix (craft_)
6. Run ‘php craft setup’ cmd & follow instructions (Set-up admin and URL)
7. Go to Website URL (MAMP)
8. Go to Admin -> Login
9. Add config items (config > general.php >):
    - Add 'requireMatchingUserAgentForSession' => false ( fixes chrome logout bug)
    - Add 'userSessionDuration' => 7200 ( adds time to user sessions )
10. Restart server ( if applicable and refresh browser )

### DEV MODE & DEBUG BAR
1. Admin -> User -> Preferences (Development - Bottom of page) -> Checkboxes[] as needed.
2. Refresh Admin and Website

### Secure Admin Path
1. config > general.php > change 'cpTrigger'
2. .env change CP_TRIGGER= value to the config
3. Restart server

### Secure front-end headers (headless or traditional), Compression, Rewrite, etc...
1. Update 'sendPowerByHeader'
    - config > general.php > add/change sendPowerByHeader = falsw
2. Update/change .htaccess
    - See .htaccess-example from previous working project.
    - **NOTE:** Example for WP as Headless, so indexfiles etag, redirects, compression & rewrite may/maynot work as-is for craft...

### Generating User Passwords Manually
1. Add '1qaz1qaz' temp password as '$2y$13$lYYpMHSa1g7HJHSg5iysnexkm91EdpsiRwRzuGA8AO6DPnUM..Cmy' in the DB.
2. Change '1' to '0' if the users account is locked.
3. Login, and change password.


### Install Plugins
1. Redactor plugin for WYSIWYG field type.
2. Neo for nested matrix repeating fields.


### Sections, Fields, Entries, & Types
1. Sections ( Settings -> Sections -> New )
    - Channel (Related / Similiar Items ex: Articles, Blogs, Tagged items, etc...)
    - Structure (... ex: Routes and/or Pages (Heirarchy): /about, /about/offices)
    - Single (One-off single instance and/or Unique type ex: homepage)
2. Matric Blocks, Fields & Field Types ( Defines content types store in entries )
    - Matrix blocks are groupings of fields an editor can use to build and rearrange content
    - List of Field Types: https://craftcms.com/docs/3.x/assets-fields.html#settings
3. Entries (Defines content stored in 'Sections')
4. Templates ( Defines how content is displayed to the end user )
5. Globals ( Define minimal changing content available globally for all templates. ex: footer copywrite info)
6. Assets ( Define project’s media and document files (“assets”) just like entries and other content types.)
7. Categories & Tags
    - Catrgories & Groups: Define taxonomies for entries, users, assets, etc...
    - Tags: You can create folksonomies for your entries, users, and assets using Tags.

### Routing & Dynamic Route
1. Standard Routing in CMS
    - Setting -> Routes -> New Route
    - 'blog/(slug)' - apply to template 'blog/article'
    - templates
        - Create new folder 'blog'
        - Create new file 'article.twig'
    - Info:
        - Generates entries to config -> project -> routes
        - Assign Rout path and template: https://craftcms.com/docs/3.x/routing.html
2. Dynamic Routing w/ URL Rules Manually for Plugins and Headless
    - Advanced Routing with URL Rules: https://craftcms.com/docs/3.x/routing.html#advanced-routing-with-url-rules
    - Custom Controllers & Templates
        - config/routes.php
        - https://craftcms.com/docs/3.x/extend/controllers.html
        - https://docs.craftcms.com/api/v3/craft-web-controller.html