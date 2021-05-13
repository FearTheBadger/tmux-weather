# Tmux Weather

Tmux plugin that displays weather forecast using [wttr.in](http://wttr.in) in the status bar.

The plugin introduces a new `#{forecast}` format.

Thanks to [Rahul Rai](https://github.com/rahulrai-in) for the inspiration, I just packaged it. 😉

## Usage

Add `#{forecast}` to your existing `status-right` tmux option:

```bash
set -g status-right '#{forecast} | #H'
```

You'll now see some information like so:

```
Partly cloudy +13°C ↘13km/h | AaronSB2
```

## Customisation

By default the format string used is `%C+%t+%w`, but you can override this with the `@forecast-format` option:

```bash
set -g @forecast-format %C
```

Refer to `wttr.in` [documentation](https://github.com/chubin/wttr.in/blob/master/README.md#one-line-output) for format options.

## Installation with [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

```bash
set -g @plugin 'aaronpowell/tmux-weather'
```

Hit `prefix + I` to fetch the plugin and source it.

`#{forecast}` interpolation should now work.

### Manual Installation

Clone the repo:

```bash
$ git clone https://github.com/aaronpowell/tmux-weather ~/clone/path
```

Add this line to the bottom of `.tmux.conf`:

```bash
run-shell ~/clone/path/weather.tmux
```

Reload TMUX environment:

```bash
# type this in terminal
$ tmux source-file ~/.tmux.conf
```

`#{forecast}` interpolation should now work.

## License

[MIT](LICENSE)
