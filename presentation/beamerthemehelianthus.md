# Aspect ratio
The aspect ratio of the slide is defined by the beamer class. The default aspect ratio is 4:3, to use an aspect ratio of 16:9, use `\documentclass[aspectratio=169]{beamer}` at the beginning of the document.

# Use the theme
The theme can be used with `\usepackage{path to the style file}` in preamble.

# Components

The following components follow the default beamer definition

- `\author`
- `\institute`
- `\date`
- `\title`
- `\subtitle`
- `\logo`
- `\titlegraphic`

Additional components that have been defined are

- `\backgroundimage` ([Backgrounds](#backgrounds))
- `\titlebackgroundimage` ([Backgrounds](#backgrounds))
- `\sectionbackgroundimage` ([Backgrounds](#backgrounds))
- `\leftfooter` ([Footers](#footers))
- `\rightfooter` ([Footers](#footers))

# Color

The following colors are redefined:
```
\definecolor{darkblue}{rgb}{0,0.2,0.45}
\definecolor{lightblue}{rgb}{0.15,0.66,0.88}
\definecolor{orange}{rgb}{0.97,0.58,0.12}
\definecolor{red}{HTML}{F44336}
```

# Logo and Titlegraphic

`\logo` defines the display of the logo on regular slides, whereas `\titlegraphic` defines the display of the logo on the title page. In both types of pages, the display of the logo anchors at the top right corner of the slide.

As `\logo` and `\titlegraphic` do not support newline, a `minipage` environment can be used to provide a multiline content, for example,

```
\titlegraphic{
  \begin{minipage}{.1\paperwidth}
    \includegraphics[width=\linewidth]{image 1 path}
    \\
    \includegraphics[width=\linewidth]{image 2 path}
  \end{minipage}
}
```

# Footers

Two footers are available - left and right. The left footer is defined with `\leftfooter{some content}` and the right footer is defined similarly with `\rightfooter{some content}`. The definition right footer would not affect the display of frame number. 

## Color and font theme

The colors and fonts of the left and right footers follows the `beamercolor` and `beamerfont` of the names `leftfooter` and `rightfooter` respectively.

# Custom style commands

Four custom style commands are created corresponding to the four slide styles,
1. title page - `\settitlepagestyle`
2. (sub)section page - `\setsectionpagestyle`
3. normal page with background (background page) - `\setbackgroundstyle`
4. normal page without background (content page) - `\setcontentstyle`

Issue the respective command to change the style of the slides that follows until other style commands are called.

## Default styles

### Navigation symbols

Only the content page consists of navigation symbols at the bottom of the slide, above the footers. Other pages will have no navigation symbols.

### Logo

The (sub)section page and the background page consist of no logo. The title page uses `\titlegraphic` and the content page uses `\logo` to define the logo on the page ([Logo and Titlegraphic](#logo-and-titlegraphic)).

### Background

The explanation of backgrounds refers to [Backgrounds](#backgrounds).

# Backgrounds

There are three types of slides with background
- normal page with background
- section page
- title page

For each background, there are three properties that can be modified
1. background image
2. background tint
3. background tint opacity

The background tint is the color of the mask behind the content, on top of the background image, created with the background tint opacity.

## Normal page with background

This slide style is set using `\setbackgroundstyle`.

### Background image
Background image for normal page is defined using `\backgroundimage{image path}`.

### Background tint
The background tint for normal page is defined using `\setbackgroundtint{color}` with the default color as `white`.

### Background tint opacity
The background tint for normal page is defined using `\setbackgroundtintopacity{degree}` with the default degree as 0.

## Section page

This slide style is set using `\setsectionpagestyle`.

### Background image
Background image for section page is defined using `\sectionbackgroundimage{image path}`.

### Background tint
The background tint for section page is defined using `\setsectionbackgroundtint{color}` with the default color as `white`.

### Background tint opacity
The background tint for section page is defined using `\setsectionbackgroundtintopacity{degree}` with the default degree as 0.

## Title page

This slide style is set using `\settitlepagestyle`.

### Background image
Background image for title page is defined using `\titlebackgroundimage{image path}`.

### Background tint
The background tint for title page is defined using `\settitlebackgroundtint{color}` with the default color as `white`.

### Background tint opacity
The background tint for title page is defined using `\settitlebackgroundtintopacity{degree}` with the default degree as 0.8.

# Custom beamer templates

Templates are defined for different components for adjustment. These templates can be used after the [style commands](#custom-style-commands) are used to modify the slide style. These templates can be activated with `\setbeamertemplate{component}[template]`

| Component | Template | Description |
| --------- | -------- | ----------- |
| navigation symbols | `helianthus` | navigation symbols as shown in default content slide |
| | `helianthusnonavi` | no navigation symbols |
| footline | `helianthus` | footline with left and right footer |
| | `helianthusnofoot` | hide footline |
| | `helianthusdatefoot` | footline with no color and just a date on the right |
| background canvas | `helianthus` | no background image |
| | `helianthusbackground` | using `backgroundimage`, `backgroundtint`, and `backgroundtintopacity` to format background | 
| | `helianthustitle` | using `titlebackgroundimage`, `titlebackgroundtint`, and `titlebackgroundtintopacity` to format background |
| | `helianthussection` | using `sectionbackgroundimage`, `sectionbackgroundtint`, and `sectionbackgroundtintopacity` to format background |
| sidebar right | `helianthus` | `logo` is displayed |
| | `helianthusnologo` | no logo |
| | `helianthustitle` | `titlegraphic` is displayed |


# Title page

Before the title page is created, the command `\settitlepagestyle` should be issued.

Title page created with `\maketitle` or `\titlepage` (in a frame) consists of the following components left-aligned:

- title
- subtitle
- author
- institute

All these components uses the `default` beamer templates. For example, to make the title center-aligned, deploy the command

```\setbeamertemplate{title}[default][center]```

before creating the title page. `subtitle`, `author`, and `institute` can also be modified in the same manner.


To display logo on the title page, refers to the section of [Logo and Titlegraphic](#logo-and-titlegraphic).

# Blocks

Three block environments are formatted
- normal block - `block`
- alert block - `alertblock`
- example block - `exampleblock`

# Attribution of images used in sample tex file
- petronas-towers-1222083.jpg: Photo by user HedonistZg on Freeimages.com
- the-great-cave-1531993.jpg: Photo by user Scmatchmo on Freeimages.com
- batu-1208710.jpg: Photo by user otjep on Freeimages.com
- Galaxy-backgrpund-01-hq: Photo by user Vexels.com on Freeimages.com
- nature-creek-mountain-design-5690340.png: Photo by user Vexels.com on Freeimages.com
- snowy-mountain-river-scene-png-5690341.png: Photo by user Vexels.com on Freeimages.com
