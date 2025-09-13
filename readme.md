 
```
.___________. __________   ___ .___________. _______  __        ______     ______   .______      .______   
|           ||   ____\  \ /  / |           ||   ____||  |      /  __  \   /  __  \  |   _  \     |   _  \  
`---|  |----`|  |__   \  V  /  `---|  |----`|  |__   |  |     |  |  |  | |  |  |  | |  |_)  |    |  |_)  | 
    |  |     |   __|   >   <       |  |     |   __|  |  |     |  |  |  | |  |  |  | |      /     |   ___/  
    |  |     |  |____ /  .  \      |  |     |  |     |  `----.|  `--'  | |  `--'  | |  |\  \----.|  |      
    |__|     |_______/__/ \__\     |__|     |__|     |_______| \______/   \______/  | _| `._____|| _|      
                                                                                                            
```

textfloorp is a fork of textfox (https://github.com/adriankarlen/textfox) modified specifically for Floorp. Mostly meant for personal use.

Readme in progress.

## Preview

Available later.
> `textfloorp tries to not hard code any colors, [Firefox Color extension](https://addons.mozilla.org/en-US/firefox/addon/firefox-color/) is the
> recommended approach to coloring Firefox with `textfox`.

## Prequisites

- Sidebery (optional)

## Installation

### Manual

1. Download the files
2. Go to `about:profiles`
3. Find your profile -- ( _„This is the profile in use and it cannot be deleted.”_ )
4. Open the profile's root directory
5. Move the files chrome directory and user.js there
6. Restart Firefox

> [!IMPORTANT]
> textfox now supports horizontal tabs, to enable them change the
> `--tf-display-horizontal-tabs` variable in your `config.css` to `block`. See
> [CSS configurations](#css-configurations) for more info.

> [!NOTE]
> If you don't want to use the provided user.js, please read through it and
> apply the settings in `about:config` manually. These are needed for the css to
> work.

## Unsupported Settings
Some settings in Firefox or Floorp do not work.
### Firefox Settings
> Currently only horizontal tabs work properly
### Floorp Settings
> Floorp sidebar is intended to be on the right. Margin has to be manually edited for sidebar on the left.


### Sidebery

Sidebery css is being set from within `content/sidebery` (applied as content to
the sidebery url). If you have any prexisting css set from within the sidebery
settings, they might clash or make it so that the sidebery style does not match
the example.

#### Settings

The theme was made using a reset sidebery config, so there should not be
anything crazy needed here, notable settings being set is using the **plain**
theme and **firefox** color scheme. If you want to you can import the sidebery
settings provided.

> [!IMPORTANT]
> **Importing sidebery settings overwrites your current settings, do this at
> your own risk.**

## Customization

The icon configuration utilizes code that is originally from ShyFox, therefore
the same settings are used (these can be set in about:config).
| Setting | true | false (default) |
| -------------------------------------- | --------------------------------------------------------------------- | ------------------------- |
| `shyfox.enable.ext.mono.toolbar.icons` | Supported extensions get monochrome icons as toolbar buttons | Standard icons used |
| `shyfox.enable.ext.mono.context.icons` | Supported extensions get monochrome icons as context menu items | Standard icons used |
| `shyfox.enable.context.menu.icons` | Many context menu items get icons | No icons in context menus |

### CSS configurations
The theme ships with a `defaults.css`, this file can be overriden by creating a
`config.css` inside the chrome directory. For instance if I'd want to change the
border radius it would look like this:

```css
/* path: chrome/config.css */
:root {
  --tf-rounding: 4px;
}
```

### Changing the new tab logo

The new tab logo can be any string you want, to create a string with line breaks
add a `\A` at every line break, also make sure to break any backslashes, eg. if
you want a `\`, you need to write `\\`. I used [this tool](https://www.patorjk.com/software/taag/#p=display&f=Slant&t=textfox)
to create the current logo.

Wanna hide the logo? Simply pass an empty string as the logo.

## Acknowledgements
All credit to [AdrianKarlen](https://github.com/adriankarlen) for making the orignal [textfox](https://github.com/adriankarlen/textfox) .

[Naezr](https://github.com/Naezr) for contributing icon logic and some sideberry logic to textfox.