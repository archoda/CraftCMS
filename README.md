1. Manual Download of Craft CMS for OSX
    - OR - COPY CMS FILES and EXPORT SQL ( https://craftcms.com/knowledge-base/duplicating-a-craft-site)
2. Create Website URL / LocalHost (MAMP)=
    - ENSURE PHP < 8 TO NOT REQUIRE GD/ImageMagic
    - https://samsonasik.wordpress.com/2021/01/04/install-imagick-extension-for-php8-in-macos-big-sur/
3.	Copy/Paste CraftCMS to Localhost -> web directory
4.	Create MySQL database + privileges ( IMPORTANT: collate as utf8_unicode_ci )
5.	Update .env file for Driver, Server, MySQL/Port, DB Name, User, Password, Prefix (craft_)
6.	Run ‘php craft setup’ cmd & follow instructions (Set-up admin and URL)
7.	Go to Website URL (MAMP)
8.	Go to Admin -> Login
