# Create a plugin in five simple steps
You can create a WordPress plugin in five simple steps. Let me show you how…

# 1. FTP into your site
The first thing you'll need to do is access your site via FTP using the FTP program of your choice (mine is Coda). If you're not familiar with FTP, I recommend you read up on that before moving forward.

# 2. Navigate to the WordPress plugins folder
Once you've accessed your site via FTP, you'll need to navigate to the WordPress plugins folder. That folder is almost always located at /wp-content/plugins.

# 3. Create a new folder for your plugin
Now that you're in the plugins folder it's time to create a folder for yours! Go ahead and create a new folder, giving it a unique name using lowercase letters and dashes such as my-first-plugin. Once you've done that, enter your new folder and move on to the next step.

# 4. Create the main PHP file for your plugin
Next, you'll need to create the main file for your plugin. To do so, create a PHP file within your new plugin folder and give it the same name such as my-first-plugin.php. After you've done that, open your plugin's main file and get ready to do some editing.

# 5. Setup your plugin's information
Finally, copy and paste the plugin information below into your main plugin file. Make sure to edit the details such Plugin Name and Plugin URI as they pertain to your plugin.
```
<?php
/**
 * Plugin Name: My First Plugin
 * Plugin URI: http://www.mywebsite.com/my-first-plugin
 * Description: The very first plugin that I have ever created.
 * Version: 1.0
 * Author: Your Name
 * Author URI: http://www.mywebsite.com
 */
```
That's it! You've just completed the minimum number of steps that are required to create a WordPress plugin. You can now activate it within the WordPress admin and revel in all of your glory.

What now?
At this point you're probably wondering what this plugin is supposed to do. Well, it doesn't do anything! I said I would show you how to create a plugin, I didn't say I'd show you how to create a plugin that does anything. 🙂

All kidding aside, the goal of this post is to illustrate just how simple it is to get started creating WordPress plugins. Whip one up with the steps outline above and you're ready to start making things happen.

# Making your plugin do something simple

The easiest way to make things happen in WordPress is with actions and filters. Let's explore that by creating a simple action that adds a line of text below all of the posts on your site. Copy and paste this code into your main plugin file (below the plugin information) and save it.
```
add_action( 'the_content', 'my_thank_you_text' );

function my_thank_you_text ( $content ) {
    return $content .= '<p>Thank you for reading!</p>';
}
```
This code hooks into “the_content” action that fires when WordPress renders the post content for your site. When that action fires, WordPress will call our “my_thank_you_text” function that is defined below the “add_action” call.