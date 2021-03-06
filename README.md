Modific
=========

Modific is a ST2 plugin for highlighting lines changed from the last commit (you know what I mean if you used Netbeans).

For now it supports **Git**, **SVN** and **Mercurial**.


Install
-------

The easiest way to install is through **[Package Control](http://wbond.net/sublime\_packages/package\_control)**.

Once you install Package Control, restart ST2 and bring up the Command Palette (`Ctrl+Shift+P` on Linux/Windows, `Cmd+Shift+P` on OS X). Select "Package Control: Install Package", wait while Package Control fetches the latest package list, then select *Modific* when the list appears. The advantage of using this method is that Package Control will automatically keep *Modific* up to date with the latest version.

Or you can **download** the latest source from [GitHub](https://github.com/gornostal/Modific/zipball/master) and copy the *Modific* folder to your Sublime Text "Packages" directory.

Or **clone** the repository to your Sublime Text "Packages" directory:

    git clone git://github.com/gornostal/Modific.git


The "Packages" directory is located at:

* OS X:

        ~/Library/Application Support/Sublime Text 2/Packages/

* Linux:

        ~/.config/sublime-text-2/Packages/

* Windows:

        %APPDATA%/Sublime Text 2/Packages/

Please, make sure your VCS binaries is in the PATH (**especially if you are on Windows**).

To do that on Windows, open `Controll Panel -> System -> Advanced system settings -> Environment variables -> System Variables`, find PATH, click "Edit" and append `;C:\path\to\VCS\binaries` for every VCS you will use (or make sure it's already there).

Features / Usage
----------------

**Highlight changes** *(automatically: on save or when window gets focus)*
[![Highlight changes](http://i.imgur.com/FgpyRl.jpg)](http://i.imgur.com/FgpyR.jpg)

**Show diff** `Ctrl+Alt+D` on Linux/Windows, `Ctlr+Super+D` on OS X
[![Show diff](http://i.imgur.com/csCw7l.jpg)](http://i.imgur.com/csCw7.jpg)

**Preview of the commited code for current line** `Ctrl+Alt+C` on Linux/Windows, `Ctlr+Super+C` on OS X
[![Preview](http://i.imgur.com/siVOXl.jpg)](http://i.imgur.com/siVOX.jpg)

**Revert modification** `Ctrl+Alt+R` on Linux/Windows, `Ctlr+Super+R` on OS X

This command reverts modifications if your cursor stays on modified line (or if on group of lines, then whole group will be reverted)

**Go through changed lines** `Ctrl+Shift+Page Up(Down)`

For those who expected to see a clone of Netbeans feature - unfortunately, with existing ST2 API that is impossible :(

Configuring
-----------

Open `Prefrences -> Package Settings -> Modific -> Settings - Default` and look for available settings.

If you want to change something, don't do it in this file. Open `Preferences -> Package Settings -> Modific -> Settings - User` and put there your configuration.

You can configure is a type of icon (dot, circle or bookmark) and path for your VCS binaries (or leave them as is, if you have them in your PATH). It's also possible to set priority for VCS used (when you have more than one simultaneously) by reordering their definitions.

If some sacred punishment has been bestowed upon you, and you have no other choice but to use OS, where console has non-UTF8 encoding, you can set console_encoding parameter to the name of your beloved encoding. This parameter is specifically designed for Windows XP users, who have their git repositories in folders with cyrillic path. Since russian XP uses CP1251 as default encoding (including console), VCS diff commands will be encoded appropriately, when using this parameter.

Known issues
------------

_Issue #9_: Sometimes disappear icons in the gutter and the tabs row.
If you experience that, try to restart the editor (sometimes it helps).

If you know exactly how to reproduce those issues, please write a comment [here](https://github.com/gornostal/Modific/issues/9).

My guess is there is a bug in Sublime when plugin use `add_regions` API.

License
-------
Released under the [WTFPLv2](http://sam.zoy.org/wtfpl/COPYING).
