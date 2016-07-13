![image](https://scontent.fgig1-1.fna.fbcdn.net/v/t1.0-9/1908347_267402813463714_2640413290531538257_n.png?oh=d5ff3cd7928ee08a74145c8e14a0c658&oe=58288439)

# Mobidick Theme

The officially un-official [Yeoman](https://github.com/yeoman/yeoman) Generator for [WordPress](http://wordpress.org/).  I magically take you from scratching your head wondering where to start, all the way to running the famous 5-minute install.  I have configuration options that will WOW you.  If you use Git, I can *git* you off the ground with WordPress as a submodule just by following a couple of prompts.  Have a custom base theme you always start your projects off with?  You can install that too, either straight from GitHub or by pointing me to a tarball.  Other things I do:

- Custom directory configuration
- Install WordPress as a Git submodule for easy version controlled updates
- Theme init hook for when you install a new theme
- Permission setting on install
- Create your database, all you have to do is make me a user
- Built in Vagrant configuration
- *New* Set custom defaults with `.mobidick` files
- *New* Environment based wp-config files, `local-config.php`

## How To Use

If you do not already have the Yeoman toolset installed do so now, and might as well install me at the same time *(NOTE: don't type the `$`)*:

	$ npm install -g yo generator-mobidick

While running if you get errors try running as super user:

	$ sudo npm install -g yo generator-mobidick

And run me:

	$ yo mobidick

Follow my prompts and WA-BAM....ASCII art!!!!

![image](http://wesleytodd.com/media/posts/yeopress-a-yeoman-generator-for-wordpress/yeopress-ascii-art.png)

### Advanced Usage

By specifying the `--advanced` flag you get access to more features:

- Vagrant: Sets up a Vagrant box using Puppet with all the requirements for running a WordPress site.
- WP version: Select a specific WordPress version to install
- Block external requests: Adds the `WP_HTTP_BLOCK_EXTERNAL` setting to config to lock down the admin
- Add core files to gitignore: Adds rules to the `.gitignore` file for the WordPress core files

### Reusing common settings

You probably want to be able to quickly zip through your install with similar settings for every project.  For example, you probably always want to use git but the default is no git.  You can define any custom defaults you want in `~/.mobidick`.  This file is just a json file with key-value pairs for the config settings you want.  Here is an example:

```json
{
	"git": true,
	"dbHost": "localhost",
	"dbName": "mobidick",
	"dbUser": "mobidick",
	"dbPass": "mobidick"
}
```

For a full example, open up the local `.mobidick` file that is created by the generator.  This file is located in the directory you ran `yo mobidick` in.

## Installing WordPress Plugins

New with `v1.4.0` is a subgenerator for installing plugins, `yo mobidick:plugin`.  You can supply a comma delimited list of plugin slugs to download.  mobidick will download and unzip those plugins into your content directory.

<!-- ### Visual Learner??

[Watch the video](http://www.youtube.com/watch?v=Em-NMCgNhhY).

ADD Visual Learner?  [Watch the shorter video](http://www.youtube.com/watch?v=WSG0P5VpSUk).

[Also see the wiki](https://github.com/wesleytodd/mobidick/wiki)

[And here is the boring write-up...](http://wesleytodd.com/2013/5/mobidick-a-yeoman-generator-for-wordpress.html) -->

## Themes

Custom themes can be installed from GitHub or a Tarball.  Once installed, they are responsible for their own Gruntfile and related tasks.  A basic example template can be found in the [template branch](https://github.com/wesleytodd/mobidick/tree/template) of this repo.  The example template comes with a few grunt tasks pre-configured:

- Regarde ([grunt-regarde](https://npmjs.org/package/grunt-regarde))
- Live Reload ([grunt-contrib-livereload](https://npmjs.org/package/grunt-contrib-livereload))
- Sass ([grunt-contrib-sass](https://npmjs.org/package/grunt-contrib-sass))
- JSHint ([grunt-contrib-jshint](https://npmjs.org/package/grunt-contrib-jshint))
- Bower ([grunt-bower-requirejs](https://npmjs.org/package/grunt-bower-requirejs))
- RequireJS ([grunt-contrib-requirejs](https://npmjs.org/package/grunt-contrib-requirejs))

