
[![★](https://img.shields.io/github/stars/cronvel/terminal-kit.svg?label=❤)](https://github.com/cronvel/terminal-kit/stargazers)
[![License](https://img.shields.io/github/license/cronvel/terminal-kit.svg)](https://github.com/cronvel/terminal-kit)
[![Downloads](https://img.shields.io/npm/dm/terminal-kit.svg)](https://www.npmjs.com/package/terminal-kit)
[![Version](https://img.shields.io/npm/v/terminal-kit.svg)](https://www.npmjs.com/package/terminal-kit)
[![Codewake](https://www.codewake.com/badges/ask_question.svg)](https://www.codewake.com/p/terminal-kit)

[![Stats](https://nodei.co/npm/terminal-kit.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/terminal-kit)



# Terminal Kit

A full-blown terminal lib featuring: 256 colors, styles, keys & mouse handling, input field, interactive 'yes or no', 
screen buffer, and many more...

Whether you just need colors & styles, build a simple interactive command line tool or a complexe terminal application:
this is the absolute terminal lib for Node.js!

It does **NOT** depend on ncurses.

* License: MIT
* Current status: **really close to release!**

Some tutorials are available at [blog.soulserv.net/tag/terminal](http://blog.soulserv.net/tag/terminal/).



## Screenshot, PleaZe!

This is a fraction of what Terminal-Kit can do, with only few lines.
Click any image to see the documentation related to the feature!

[![Styles output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/style-doc1.png)](doc/low-level.md)

[![Input field output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/input-field-doc1.gif)](doc/high-level.md#ref.inputField)

[![Input field output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/input-field-doc2.gif)](doc/high-level.md#ref.inputField)

[![Single line menu output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/single-line-menu-doc1.gif)](doc/high-level.md#ref.singleLineMenu)

[![Progress bar output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/progress-bar-doc1.gif)](doc/high-level.md#ref.progressBar)

[![Progress bar output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/progress-bar-doc2.gif)](doc/high-level.md#ref.progressBar)

[![Slow typing output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/slow-typing-doc1.gif)](doc/high-level.md#ref.slowTyping)

[![Yes or no output](https://raw.githubusercontent.com/cronvel/terminal-kit/master/sample/yes-no-doc1.gif)](doc/high-level.md#ref.yesOrNo)

[![Spaceship](https://raw.githubusercontent.com/cronvel/terminal-kit/master/demo/record.gif)](doc/screenbuffer.md)



## Key features

* [colors, 256 colors or even 24 bits colors](doc/low-level.md#ref.colors), if the terminal supports it
* [styles (bold, underline, italic, and many more)](doc/low-level.md#ref.styles)
* [style mixing](doc/low-level.md#ref.chainable)
* [chainable](doc/low-level.md#ref.chainable)
* [string formatting](doc/low-level.md#ref.string-formatting)
* [short style markup](doc/low-level.md#ref.style-markup)
* [terminal window title](doc/low-level.md#ref.misc)
* [cursor positioning](doc/low-level.md#ref.movingCursor)
* [keyboard input](doc/high-level.md#ref.grabInput)
* [mouse support (GPM is supported for the Linux Console)](doc/high-level.md#ref.grabInput)
* [input field](doc/high-level.md#ref.inputField)
* [interactive 'yes or no'](doc/high-level.md#ref.yesOrNo)
* [screen & off-screen buffers (a concept similar to SDL's *Surface*)](doc/screenbuffer.md#top)
* [event-driven](doc/events.md#top)
* Platform: any xterm-compatible terminal, it has been tested successfully with:
	* xterm
	* gnome-terminal
	* Konsole
	* Terminator
	* xfce4-terminal
	* Linux Console
	* rxvt/urxvt
	* Eterm
	* Terminology
	* **Your terminal?** Help tracking terminal compatibilities [on github!](https://github.com/cronvel/terminal-kit/issues)



## Quick examples

```js
// Require the lib, get a working terminal
var term = require( 'terminal-kit' ).terminal ;

// The term() function simply output a string to stdout, using current style
// output "Hello world!" in default terminal's colors
term( 'Hello world!\n' ) ;

// This output 'red' in red
term.red( 'red' ) ;

// This output 'bold' in bold
term.bold( 'bold' ) ;

// output 'mixed' using bold, underlined & red, exposing the style-mixing syntax
term.bold.underline.red( 'mixed' ) ;

// printf() style formatting everywhere:
// this will output 'My name is Jack, I'm 32.' in green
term.green( "My name is %s, I'm %d.\n" , 'Jack' , 32 ) ;

// Since v0.16.x, style markup are supported as a shorthand.
// Those two lines produce the same result.
term( "My name is " ).red( "Jack" )( " and I'm " ).green( "32\n" ) ;
term( "My name is ^rJack^ and I'm ^g32\n" ) ;

// Width and height of the terminal
term( 'The terminal size is %dx%d' , term.width , term.height ) ;

// Move the cursor at the upper-left corner
term.moveTo( 1 , 1 ) ;

// We can always pass additional arguments that will be displayed...
term.moveTo( 1 , 1 , 'Upper-left corner' ) ;

// ... and formated
term.moveTo( 1 , 1 , "My name is %s, I'm %d.\n" , 'Jack' , 32 ) ;

// ... or even combined with other styles
term.moveTo.cyan( 1 , 1 , "My name is %s, I'm %d.\n" , 'Jack' , 32  ) ;
```


### [I want to READ THE DOC NOW!](doc/documentation.md#ref.TOC)


