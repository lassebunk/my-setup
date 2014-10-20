# My Mac Setup

This is a list of programs and apps I use on my Mac. I found a lot of this by looking at other people's lists, so maybe you can too.
Let me know in the issues if you have any questions.

## Software

1. Latest OS X
   
1. [Firefox](http://www.mozilla.org/firefox)

   Web browser.

   * [JSONView](https://addons.mozilla.org/en-US/firefox/addon/10869/)

     View JSON documents in the browser.

   * [Firebug](https://addons.mozilla.org/en-US/firefox/addon/firebug/)

     Development tools and debugging.

   * [Web Developer](https://addons.mozilla.org/en-US/firefox/addon/web-developer/)

     Web developer tools.

1. [Dropbox](https://www.dropbox.com/)

   Sync files between computers + backup.

1. [Sublime Text](http://www.sublimetext.com/)

   Code and text editor.

   * Add `subl` command:

     ```
     $ sudo ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /bin/subl
     ```

   * [Package Manager](https://sublime.wbond.net/installation)
   * *Markdown Preview* package via *Install Package*

1. [Witch](https://itunes.apple.com/dk/app/witch/id412485838?mt=12)

   Alt+Tab between app windows (what I use it for).

1. [GitHub for Mac](http://mac.github.com/)

   GitHub GUI client.

1. [iTerm2](http://www.iterm2.com/)

   Terminal app.

   * Add beginning/end of line/word, in *Preferences &rarr; Keys*:

     For | Action               | Send
     ----|----------------------|------
     ⌘←  | Hex code             | 0x01 
     ⌘→  | Hex code             | 0x05
     ⌥←  | Send escape sequence | b
     ⌥→  | Send escape sequence | f

1. [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

   Shell replacement with enhancements such as autocomplete, current git branch, shortcuts, etc.

   Add aliases for zsh, in *~/.zshrc*:

   ```bash
   source ~/Dropbox/Dev/scripts/aliases
   ```

1. [Homebrew](http://brew.sh/)

   Package manager for OS X.

1. [Curl](http://curl.haxx.se/)

   Install a new curl to ensure the latest version:

   ```
   $ brew install curl
   $ brew link curl --force
   ```

1. [Direnv](http://direnv.net/)

   Easy per-folder environment setups.
   I use this when for example I have special per-project bins for Rails projects.

   Installation:

   ```
   $ brew install direnv
   ```

   To use in zsh, at the end of `~/.zshrc`:

   ```
   eval "$(direnv hook zsh)"
   ```

1. [MySQL](http://www.mysql.com/)
   
   Database server.

   ```
   $ brew install mysql
   ```

1. [Spotify](https://www.spotify.com/)

   Music app.

1. [RVM](http://rvm.io/)

   Ruby version manager and installer.

   After installing, install [Ruby](http://ruby-lang.org):

   ```
   $ rvm install 2.1.0
   ```

1. [Caffeine](https://itunes.apple.com/dk/app/caffeine/id411246225?mt=12)
   
   For keeping the screen from dimming, e.g. when watching videos.

1. [Airmail](https://itunes.apple.com/dk/app/airmail/id573171375?mt=12)

   Simple, multi-account mail app with support for Gmail / Google Apps.

1. [Adobe Photoshop](http://www.adobe.com/products/photoshop.html)

   For editing and designing graphics.

1. [Java](http://java.com/getjava)

   Needed for a Ruby gem I use, and for single-sign-on on Danish websites.

1. [Pow](http://pow.cx/)

   Rails/Rack development server that lets you serve your local development websites on internal .dev domains.
   
   **Serving PHP with Pow**
   
   Make Pow go to port 81 by default:
   
   ```
   $ echo 81 > ~/.pow/default
   ```
   
   Make Apache listen on port 81. In */etc/apache2/httpd.conf*:
   
   ```
   Listen 81
   ```
   
   Enable this module:
   
   ```
   LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so
   ```
   
   And add:
   
   ```
   <Directory "/Users/lassebunk/dev/web/">
      AllowOverride All
      Require all granted
   </Directory>

   <VirtualHost 127.0.0.1:81>
      ServerName any.dev
      ServerAlias *.dev
      VirtualDocumentRoot "/Users/lassebunk/dev/web/%1"
   </VirtualHost>
   ```
   
   And restart Apache:
   
   ```
   $ sudo apachectl -k restart
   ```

1. [ImageMagick](http://www.imagemagick.org/)

   Image manipulation and conversion. Used by a gem I use.
   
1. [f.lux](https://justgetflux.com/)
   
   Warms the screen colors at night.

## Setup

1. Hot corners in OS X

   In *System Preferences &rarr; Mission Control &rarr; Hot Corners...*:

   Corner       | Action
   -------------|---------------------
   Bottom left  | Desktop
   Bottom right | Put Display to Sleep
