### Local Installation & Set-up

1. Manual Download of Craft CMS for OSX
    - OR - COPY CMS FILES and EXPORT SQL ( https://craftcms.com/knowledge-base/duplicating-a-craft-site)
2. Create Website URL / LocalHost (MAMP)=
    - ENSURE PHP < 8 TO NOT REQUIRE GD/ImageMagic
    - https://samsonasik.wordpress.com/2021/01/04/install-imagick-extension-for-php8-in-macos-big-sur/
    - Update PHP.ini max_execution_time to 120 and memory_limit to 256M
3.	Copy/Paste CraftCMS to Localhost -> web directory
4.	Create MySQL database + privileges ( IMPORTANT: collate as utf8_unicode_ci )
5.	Update .env file for Driver, Server, MySQL/Port, DB Name, User, Password, Prefix (craft_)
6.	Run ‘php craft setup’ cmd & follow instructions (Set-up admin and URL)
7.	Go to Website URL (MAMP)
8.	Go to Admin -> Login



### Secure Admin Path
1. config > general.php > change 'cpTrigger'
2. .env change CP_TRIGGER= value to the config
3. Restart server

### Generating User Passwords Manually
1. Add '1qaz1qaz' temp password as '$2y$13$lYYpMHSa1g7HJHSg5iysnexkm91EdpsiRwRzuGA8AO6DPnUM..Cmy' in the DB.
2. Change '1' to '0' if the users account is locked.
3. Login, and change password.

### .HTACCESS FILE (Secure front-end headers, Compression, Rewrite, etc...)
1. Update/change .htaccess
    - See .htaccess-example from previous working project.
    - **NOTE:** Example for WP as Headless, so indexfiles etag, redirects, compression & rewrite may/maynot work as-is for craft...


