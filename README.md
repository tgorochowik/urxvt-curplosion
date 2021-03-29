# urxvt-curplosion

Curplosion is a cursor locator extension for urxvt.

When triggered, it produces a _curplosion_ (or cursor explosion) which is easy to spot.

![curplosion](https://user-images.githubusercontent.com/8438531/112892678-eb9a6800-90d9-11eb-8c32-ce110fb24306.gif)

The following events can trigger a curplosion (if enabled):

* manual trigger
* terminal window regaining focus
* terminal bell

This extension is especially useful when using multi-window setup (like tmux or vim with multiple splits).

## Installation

* Clone the extension into the urxvt extensions directory;

```
mkdir -p ~/.urxvt/ext/
cd ~/.urxvt/ext/
git clone https://github.com/tgorochowik/urxvt-curplosion.git curplosion
```

* Enable the extension in the `~/.Xdefaults` file:

```
urxvt.perl-ext-common: curplosion/curplosion
```

## Configuration

The configuration can be adjusted in the `~/.Xdefaults` file.

The default trigger is `C-slash`.
To change it, adjust the following setting:

```
urxvt.curplosion.trigger:  C-slash
```

Play with the following settings to adjust the looks of the cursor explosion:

```
urxvt.curplosion.colors:   5, 7, 5
urxvt.curplosion.sizes:    3, 7
```

Additionally, the duration of the curplosion can be adjusted:

```
urxvt.curplosion.duration: 50
```

The unit of the duration is a millisecond.
Also please note, that if the duration is set to a very small value the terminal might not be able to process it fast enough, and it will longer then desired.
The explosion does NOT block the terminal, so setting it to a very large value is safe as it will not prevent any other usage of the terminal.

To automatically trigger a curplosion on window focus, or on terminal bell, set the corresponding variables:

```
urxvt.curplosion.show-on-focus: true
urxvt.curplosion.show-on-bell:  true
```
