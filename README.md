# i3 4.14.1-gaps-recursive

This is my i3-gaps fork which adds support for recursive variables, as well as allows for further customization of the nagbar

## Recursive Variables

Per the i3 docs, ["Variables expansion is not recursive so it is not possible to define a variable with a value containing another variable,"](https://i3wm.org/docs/userguide.html#variables) however this fork allows just that.
An example (similar to my own `~/.config/i3/config`):

     set $HOME    "/home/USERNAME"
     set $CONFDIR "$HOME/.config/i3"
	 set $BAR     "$CONFDIR/start_bar.sh"

The value of $BAR will be `/home/USERNAME/.config/i3/start_bar.sh`.

## i3-nagbar

The i3-nagbar has been modified to provide four additional options:

     -c <text>  - Text to be placed in the "X"/cancel button
     -B <color> - Background color of the bar
     -F <color> - Background color of any buttons
     -T <color> - Text color

## Compilation and Installation

The build process remains unchanged, simply run:

     git clone "https://github.com/Cubified/i3"
	 cd i3

     autoreconf --force --install
	 mkdir build && cd build
	 ../configure --prefix=/usr --sysconfdir=/etc --disable-sanitizers
	 make

And optionally:

     sudo make install
