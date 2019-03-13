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
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <h2>Introduction</h2>
    <p> WordPress is the most popular Content Management System (CMS) for
      building a blogging system or dynamic websites. </p>
    <p>Wordpress is an open-source platform and available for free. It is fully
      customized, also has all kinds of themes and plugins available for free. </p>
    <h3>WordPress Setup</h3>
    <p>You can set up WordPress at home following the guide from the WordPress
      official website, or you can use some online hosting services. Under most
      circumstances, installing WordPress is a very simple process and takes
      less than five minutes to complete. Many web hosts offer tools to
      automatically install WordPress for you. </p>
    <h3>WordPress Configuration</h3>
    <p>After installation is done, you can try to set up a theme, install
      several plugins, learn how to write posts, upload media, create pages, add
      users, and configure settings. </p>
    <h3>WordPress Themes and Plugins</h3>
    <p>A theme controls the presentation of content; whereas a plugin is used to
      control the behavior and features of your WordPress site. </p>
    <h3>WP_DEBUG</h3>
    <p> WordPress provides several constants to support your debugging efforts.
    </p>
    <p>In wp-config.php, WP_DEBUG is used to enable debug mode. WP_DEBUG_LOG and
      WP_DEBUG_DISPLAY are additional constants for debugging. WP_DEBUG_LOG log
      all error messages to a debug.log within your WordPress /wp-content/
      directory. WP_DEBUG_DISPLAY controls whether debug messages displayed
      within the HTML of your theme pages. </p>
    <p>Besides WP_DEBUG, there are also some plugins, guidelines and unit test
      data sets available in the WordPress community. </p>
    <h2>WordPress Themes</h2>
    <p> A WordPress theme changes the design of a WordPress website, often
      including how the site looks on the front-end. There are thousands of free
      WordPress themes free available. </p>
    <p>There are only two files absolutely required in a WordPress theme: <b><br>
      </b></p>
    <p><b>index.php:</b> the main template file <b><br>
      </b></p>
    <p><b>style.css:</b> the main style file </p>
    <p>Other files usually in a WordPress theme directory include CSS files,
      JavaScript files, or PHP files. </p>
    <h3>Theme Basics</h3>
    <p> WordPress themes use template files or template partials to express how
      the site should be displayed. For example, you would use the header.php
      template to create a header, or the comments.php template to include
      comments. The most critical template file is index.php, which is the
      catch-all template if a more-specific template cannot be found. </p>
    <p>Below is a list of some basic theme templates and files recognized by
      WordPress. </p>
    <ul>
      <li><b>404.php:</b>The 404 template is used when WordPress cannot find a
        post, page, or other content that matches the visitor’s request.</li>
      <li> <b>archive.php:</b>The archive template is used when visitors
        request posts by category, author, or date.</li>
      <li><b>archive-{post-type}.php:</b>The archive post type template is used
        when visitors request a custom post type archive.</li>
      <li> <b>attachment.php:</b>The attachment template is used when viewing a
        single attachment like an image, pdf, or other media file.</li>
      <li> <b>author.php:</b>The author page template is used whenever a
        visitor loads an author page.</li>
      <li> <b>category.php:</b>The category template is used when visitors
        request posts by category.</li>
      <li> <b>comments.php:</b>The comments template.</li>
      <li> <b>date.php:</b>The date/time template is used when posts are
        requested by date or time.</li>
      <li> <b>footer.php:</b> Footer file for generating the footer</li>
      <li> <b>front-page.php:</b>The front page template is always used as the
        site front page if it exists.</li>
      <li> <b>header.php:</b>The header template file usually contains your
        site’s document type, meta information, links to stylesheets and
        scripts, and other data.</li>
      <li> <b>home.php:</b> The home page template is the front page by
        default.</li>
      <li> <b>image.php:</b>The image attachment template is a more specific
        version of attachment.php and is used when viewing a single image
        attachment.</li>
      <li><b>index.php:</b> The main template file. Must have.</li>
      <li><b>page.php:</b>The page template is used when visitors request
        individual pages, which are a built-in template.</li>
      <li> <b>page-{slug}.php:</b>The page slug template is used when visitors
        request a specific page, for example one with the “about” slug
        (page-about.php).</li>
      <li> <b>search.php:</b> The search results template is used to display a
        visitor’s search results.</li>
      <li> <b>sidebar.php:</b> Sidebar file for generating the sidebar</li>
      <li> <b>singular.php:</b>The singular template is used for posts when
        single.php is not found, or for pages when page.php are not found. If
        singular.php is not found, index.php is used.</li>
      <li> <b>single.php:</b>The single post template is used when a visitor
        requests a single post.</li>
      <li> <b>single-{post-type}.php</b>: The single post template used when a
        visitor requests a single post from a custom post type.</li>
      <li> <b>tag.php:</b>The tag template is used when visitors request posts
        by tag.</li>
      <li> <b>taxonomy.php:</b>The taxonomy term template is used when a
        visitor requests a term in a custom taxonomy.</li>
      <li> <b>rtl.css:</b> The right-to-left stylesheet is included
        automatically if the website language’s text direction is right-to-left.</li>
      <li> <b>style.css:</b> The main stylesheet. Must have.</li>
    </ul>
    <h3>Template Tags</h3>
    <p>To dynamically display information from this template files, you can use
      functions, called template tags. For example, To include the header, use
      get_header(); to include the sidebar, use get_sidebar(); to include the
      footer, use get_footer(), etc. </p>
    <h3>Main Stylesheet</h3>
    <p> The style.css is a CSS file required for every WordPress theme. It
      controls the visual design and layout of the website pages. In style.css,
      WordPress uses the header comment section to display information about the
      theme in the Appearance (Themes) dashboard panel. <b><br>
      </b></p>
    <ul>
      <li><b>Theme Name (*):</b> Name of the theme. </li>
      <li><b>Theme URI:</b>The URL of a public web page where users can find
        more information about the theme. </li>
      <li><b>Author (*):</b> The name of the individual or organization who
        developed the theme. Using the Theme Author’s wordpress.org username is
        recommended. </li>
      <li><b>Author URI:</b> The URL of the authoring individual or
        organization. </li>
      <li> <b>Description (*):</b> A short description of the theme. </li>
      <li><b>Version (*):</b> The version, written in X.X or X.X.X format. </li>
      <li><b>License (*):</b>The license of the theme. </li>
      <li><b>License URI (*):</b> The URL of the theme license. </li>
      <li><b>Text Domain (*):</b> The string used for text domain for
        translation. </li>
      <li><b>Tags:</b> Words or phrases that allow users to find the theme using
        the tag filter. </li>
      <li><b>Domain Path:</b> Used so that WordPress knows where to find the
        translation when the theme is disabled. Defaults to /languages. </li>
    </ul>
    <h3>The Loop</h3>
    <p>The Loop is the default mechanism WordPress uses for outputting posts
      through a theme’s template files. How many posts are retrieved is
      determined by the number of posts to show per page defined in the Reading
      settings. Within the Loop, WordPress retrieves each post to be displayed
      on the current page and formats it according to your theme’s instructions.
    </p>
    <p>The basic loop is: </p>
    <pre lang="php">&lt;?php if ( have_posts() ) : ?&gt;
    &lt;?php while ( have_posts() ) : the_post(); ?&gt;
        ... Display post content
    &lt;?php endwhile; ?&gt;
&lt;?php endif; ?&gt;
</pre>
  </body>
</html>