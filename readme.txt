=== Files in use ===
Contributors: mukto90
Donate link: http://nazmulahsan.me
Tags: files in use, template files, theme files, plugin files, current files, loaded files
Requires at least: 3.1.0
Tested up to: 4.7
Stable tag: trunk

A simple WordPress plugin to show theme's and plugins' files that are currently in use.

== Description ==

= Key features =

* Show theme's template file of current page
* Other files that are used/included by this template files, e.g. `header.php`, `footer.php` etc
* Show plugins' files that are being used by current page
* Each of the files are hyperlinked to the file editor. You can just click and edit any of the files.
* Multiple filter hooks enabled. For example, you can decide either you want to show plugins' files in the list or not.

== Installation ==

1. Upload \`files-in-use\` to the \`/wp-content/plugins/\` directory
2. Activate the plugin through the 'Plugins' menu in WordPress

== Screenshots ==

1. Showing files in use in admin bar

== Frequently Asked Questions ==

= How to show/hide included child files along with main template file? =

There is a filter hook `cb_monitor_show_included_files` to show/hide child files.
e.g.
`function my_function_to_show_child_files( $show ){
	return true; // use false to hide
}
add_filter( 'cb_monitor_show_included_files', 'my_function_to_show_child_files' );`

= How to show/hide plugins' files that are currently in use? =

Use filter hook `cb_monitor_show_plugin_files` to show/hide plugins' files.
e.g.
`function my_function_to_show_plugins_files( $show ){
	return true; // use false to hide
}
add_filter( 'cb_monitor_show_plugin_files', 'my_function_to_show_plugins_files' );`

= Are there any other hooks available? =

Yes, there are 5 filter hooks available.

`
// show/hide child files
apply_filters( 'cb_monitor_show_included_files', true );

// show/hide theme files
apply_filters( 'cb_monitor_show_theme_files', true );

// show/hide plugins' files
apply_filters( 'cb_monitor_show_plugin_files', false );

// set a label for the menu
apply_filters( 'cb_monitor_menu_label', '<strong style="font-weight:bold;color:#fff">Files in use: </strong>' );

// add/remove menu meta
apply_filters( 'cb_monitor_menu_meta', array( 'target' => '_blank' ) );`

== Changelog ==

= 1.1 - 02.03.2017 =
* [fix] Warning error fix

= 1.0 =
* Initial release