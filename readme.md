 
```
.___________. __________   ___ .___________. _______  __        ______     ______   .______      .______   
|           ||   ____\  \ /  / |           ||   ____||  |      /  __  \   /  __  \  |   _  \     |   _  \  
`---|  |----`|  |__   \  V  /  `---|  |----`|  |__   |  |     |  |  |  | |  |  |  | |  |_)  |    |  |_)  | 
    |  |     |   __|   >   <       |  |     |   __|  |  |     |  |  |  | |  |  |  | |      /     |   ___/  
    |  |     |  |____ /  .  \      |  |     |  |     |  `----.|  `--'  | |  `--'  | |  |\  \----.|  |      
    |__|     |_______/__/ \__\     |__|     |__|     |_______| \______/   \______/  | _| `._____|| _|      
                                                                                                            
```

_TextFox (https://github.com/adriankarlen/textfox) modified specifically for Floorp_

Ignore the readme for now.

## Preview

![image](https://github.com/adriankarlen/textfox/blob/main/misc/vertical-tabs.png)

![image](https://github.com/adriankarlen/textfox/blob/main/misc/horizontal-tabs.png)

> [!NOTE]
> The color scheme used in the pictures is [Rosé Pine Moon](https://github.com/rose-pine/firefox).
> `textfox` tries to not hard code any colors, [Firefox Color extension](https://addons.mozilla.org/en-US/firefox/addon/firefox-color/) is the
> recommended approach to coloring Firefox with `textfox`.

## Prequisites

- Sidebery (optional)

## Installation

### Installation script

1. Download/clone the repo.
2. Inside the download run `sh tf-install.sh` and follow the script
   instructions.

> [!IMPORTANT]
> This script automates file writes, use with caution. 

> [!NOTE]
> The installation script copies to contents of the repos `chrome` directory to
> the path specified, this way your `config.css` or any other `css`-files not
> part of the repo will be kept.

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

#### Defaults
```css
:root {
  --tf-font-family: "SF Mono", Consolas, monospace; /* Font family of config */
  --tf-font-size: 14px; /* Font size of config */
  --tf-accent: var(--toolbarbutton-icon-fill); /* Accent color used, eg: color when hovering a container  */
  --tf-bg: var(--lwt-accent-color, -moz-dialog); /* Background color of all elements, tab colors derive from this */
  --tf-border: var(--arrowpanel-border-color, --toolbar-field-background-color); /* Border color when not hovered */
  --tf-border-transition: 0.2s ease; /* Smooth color transitions for borders */
  --tf-border-width: 2px; /* Width of borders */
  --tf-rounding: 0px; /* Border radius used through out the config */
  --tf-margin: 0.8rem; /* Margin used between elements in sidebery */
  --tf-text-transform: none; /* Text transform to use */
  --tf-display-horizontal-tabs: none; /* If horizontal tabs should be shown, none = hidden, block = shown */
  --tf-display-window-controls: none; /* If the window controls should be shown (won't work with sidebery and hidden horizontal tabs), none = hidden, flex = shown */ 
  --tf-display-nav-buttons: none; /* If the navigation buttons (back, forward) should be shown, none = hidden, flex = shown */
  --tf-display-urlbar-icons: none; /* If the icons inside the url bar should be shown, none = hidden, flex = shown */
  --tf-display-sidebar-tools: flex; /* If the "Customize sidebar" button on the sidebar should be shown, none = hidden, flex = shown */ 
  --tf-display-titles: flex; /* If titles (tabs, navbar, main etc.) should be shown, none = hidden, flex = shown */
  --tf-newtab-logo: "   __            __  ____          \A   / /____  _  __/ /_/ __/___  _  __\A  / __/ _ \\| |/_/ __/ /_/ __ \\| |/_/\A / /_/  __/>  </ /_/ __/ /_/ />  <  \A \\__/\\___/_/|_|\\__/_/  \\____/_/|_|  ";
  --tf-navbar-margin: 8px 8px 2px; /* navbar margin */
  --tf-navbar-padding: 4px; /* navbar padding */
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