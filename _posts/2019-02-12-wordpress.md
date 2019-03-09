---
ID: 297
post_title: WordPress
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/topics/wordpress/
published: true
post_date: 2019-02-12 20:28:57
---
<h2>Introduction</h2>
WordPress is the most popular Content Management System (CMS) for building a blogging system or dynamic websites.
Wordpress is an open-source platform and available for free. It is fully customized, also has all kinds of themes and plugins available for free.
<h3>WordPress Setup</h3>
You can set up Wordpress at home following the guide from the WordPress official website, or you can use some online hosting services. Under most circumstances, installing WordPress is a very simple process and takes less than five minutes to complete. Many web hosts offer tools to automatically install WordPress for you.
<h3>WordPress Configuration</h3>
After installation is done, you can try to set up a theme, install several plugins, learn how to write posts, upload media, create pages, add users, and configure settings.
<h3>WordPress Themes and Plugins</h3>
A theme controls the presentation of content; whereas a plugin is used to control the behavior and features of your WordPress site.
<h3>WP_DEBUG</h3>
WordPress provides several constants to support your debugging efforts.
In wp-config.php, WP_DEBUG is used to enable debug mode.
WP_DEBUG_LOG and WP_DEBUG_DISPLAY are additional constants for debugging.  WP_DEBUG_LOG log all error messages to a debug.log within your WordPress /wp-content/ directory. WP_DEBUG_DISPLAY controls whether debug messages displayed within the HTML of your theme pages.
Besides WP_DEBUG, there are also some plugins, guidelines and unit test data sets available in the WordPress community.
<h2>WordPress Themes</h2>
A WordPress theme changes the design of a WordPress website, often including how the site looks on the front-end. There are thousands of free WordPress themes free available.
There are only two files absolutely required in a WordPress theme:
<b>index.php:</b> the main template file
<b>style.css:</b> the main style file
Other files usually in a WordPress theme directory include CSS files, JavaScript files, or PHP files.
<h3>Theme Basics</h3>
WordPress themes use template files or template partials to express how the site should be displayed. For example, you would use the header.php template to create a header, or the comments.php template to include comments. The most critical template file is index.php, which is the catch-all template if a more-specific template cannot be found.
Below is a list of some basic theme templates and files recognized by WordPress.
<b>404.php:</b>The 404 template is used when WordPress cannot find a post, page, or other content that matches the visitor’s request.
<b>archive.php:</b>The archive template is used when visitors request posts by category, author, or date.
<b>archive-{post-type}.php:</b>The archive post type template is used when visitors request a custom post type archive.
<b>attachment.php:</b>The attachment template is used when viewing a single attachment like an image, pdf, or other media file.
<b>author.php:</b>The author page template is used whenever a visitor loads an author page.
<b>category.php:</b>The category template is used when visitors request posts by category.
<b>comments.php:</b>The comments template.
<b>date.php:</b>The date/time template is used when posts are requested by date or time.
<b>footer.php:</b> Footer file for generating the footer
<b>front-page.php:</b>The front page template is always used as the site front page if it exists.
<b>header.php:</b>The header template file usually contains your site’s document type, meta information, links to stylesheets and scripts, and other data.
<b>home.php:</b> The home page template is the front page by default.
<b>image.php:</b>The image attachment template is a more specific version of attachment.php and is used when viewing a single image attachment.
<b>index.php:</b> The main template file. Must have.
<b>page.php:</b>The page template is used when visitors request individual pages, which are a built-in template.
<b>page-{slug}.php:</b>The page slug template is used when visitors request a specific page, for example one with the “about” slug (page-about.php).
<b>search.php:</b> The search results template is used to display a visitor’s search results.
<b>sidebar.php:</b> Sidebar file for generating the sidebar
<b>singular.php:</b>The singular template is used for posts when single.php is not found, or for pages when page.php are not found. If singular.php is not found, index.php is used.
<b>single.php:</b>The single post template is used when a visitor requests a single post.
<b>single-{post-type}.php</b>: The single post template used when a visitor requests a single post from a custom post type.
<b>tag.php:</b>The tag template is used when visitors request posts by tag.
<b>taxonomy.php:</b>The taxonomy term template is used when a visitor requests a term in a custom taxonomy.
<b>rtl.css:</b> The right-to-left stylesheet is included automatically if the website language’s text direction is right-to-left.
<b>style.css:</b> The main stylesheet. Must have.
<h3>Template Tags</h3>
To dynamically display information from this template files, you can use functions, called template tags. For example, To include the header, use get_header(); to include the sidebar, use get_sidebar(); to include the footer, use get_footer(), etc.
<h3>Main Stylesheet</h3>
The style.css is a CSS file required for every WordPress theme. It controls the visual design and layout of the website pages.
In style.css, WordPress uses the header comment section to display information about the theme in the Appearance (Themes) dashboard panel.
<b>Theme Name (*):</b> Name of the theme.
<b>Theme URI:</b> The URL of a public web page where users can find more information about the theme.
<b>Author (*):</b> The name of the individual or organization who developed the theme. Using the Theme Author’s wordpress.org username is recommended.
<b>Author URI:</b> The URL of the authoring individual or organization.
<b>Description (*):</b> A short description of the theme.
<b>Version (*):</b> The version, written in X.X or X.X.X format.
<b>License (*):</b> The license of the theme.
<b>License URI (*):</b> The URL of the theme license.
<b>Text Domain (*):</b> The string used for text domain for translation.
<b>Tags:</b> Words or phrases that allow users to find the theme using the tag filter.
<b>Domain Path:</b> Used so that WordPress knows where to find the translation when the theme is disabled. Defaults to /languages.
<h3>The Loop</h3>
The Loop is the default mechanism WordPress uses for outputting posts through a theme’s template files. How many posts are retrieved is determined by the number of posts to show per page defined in the Reading settings. Within the Loop, WordPress retrieves each post to be displayed on the current page and formats it according to your theme’s instructions.
The basic loop is:
<pre lang="php">&lt;?php if ( have_posts() ) : ?&gt;
    &lt;?php while ( have_posts() ) : the_post(); ?&gt;
        ... Display post content
    &lt;?php endwhile; ?&gt;
&lt;?php endif; ?&gt;
</pre>