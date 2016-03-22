# Linux Configuration

## Everything is a file

Doing anything even remotely close to this in Windows is mind boggingly
difficult, if not impossible. Files and settings are kept all over the place,
very often in the enigmatic registry. In Unix/Linux, EVERYTHING is a file
(<http://en.wikipedia.org/wiki/Everything_is_a_file>). Once you understand the
implications of this, it just makes sense. What is the registry and why does it
even exist?

## System Wide Configuration

Essentially all system wide configuration files are located in the `/etc`
directory.

## User Configuration

User Configuration is located in the user's home directory (`/home/[username]`/),
and mainly consists of hidden files and folders in home root or in .config/.
Many settings are located in a dedicated .config.  Syncing with Git

Since everything in Unix/Linux is a file, and ALL user related configurations
(and files) are located in their home directory, saving configurations for most
programs is a breeze. Combine this with Git and things become so awesome it is
difficult to describe.

Create a seperate directory for the dot/config files you want to sync. Init a
GIT repo in there, and use GNU Stow to symlink them.

## XORG

### Selections (Copy & Paste)

+ <http://www.jwz.org/doc/x-cut-and-paste.html>
