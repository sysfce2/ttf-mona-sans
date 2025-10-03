# Mona Sans

[Download Mona Sans](https://github.com/github/mona-sans/releases/latest) • [Typeface microsite](https://github.com/mona-sans) ↗️

A strong and versatile typeface, designed together with [Degarism](https://degarism.com/) and inspired by industrial-era grotesques. Mona Sans works well across product, web, and print. Made to work well together with  Mona Sans's sidekick, [Hubot Sans](https://github.com/github/hubot-sans).

Mona Sans is a [variable font](https://web.dev/variable-fonts/). Variable fonts enable different variations of a typeface to be incorporated into one single file, and are supported by all major browsers, allowing for performance benefits and granular design control of the typeface's weight, width, and slant.

![mona-sans](https://user-images.githubusercontent.com/99746865/200648883-dbd47e9a-9d95-483e-aef6-1bfa602eb942.png)

## Variable font usage

The design space is large, so we've split the font up into a few variable fonts.

If you want to access the whole design space, use `MonaSansVF[wdth,wght,opsz,ital]`. On the web, you can utilize points on that space like this:

```css
@font-face {
  font-family: 'Mona Sans VF';
  src:
    url('MonaSansVF[wdth,wght,opsz,ital].woff2') format('woff2 supports variations'),
    url('MonaSansVF[wdth,wght,opsz,ital].woff2') format('woff2-variations');
  font-weight: 200 900;
  font-stretch: 75% 125%;
  font-optical-sizing: auto;
}

html {
  font-family: 'Mona Sans VF';
}
```

Mona Sans includes an optical size axis (`opsz`) that automatically adjusts the font's design for optimal readability at different sizes. The optical size range spans from 1 to 100, where smaller values (1-20) are optimized for body text with improved readability, while larger values (21-100) are designed for display use with refined details and tighter spacing. When `font-optical-sizing: auto` is set, browsers will automatically select the appropriate optical size based on the font size, or you can manually control it using `font-variation-settings: "opsz" [value]`. That looks like this:

```css
.heading {
  font-variation-settings: "wght" 700, "wdth" 125, "opsz" 72; /* Bold, Expanded, Display size */
}

.body-text {
  font-variation-settings: "wght" 400, "wdth" 100, "opsz" 12; /* Regular, Normal width, Text size */
}
```

To reduce [CLS](https://web.dev/cls/), you can preload the font in the `head` of your document:

```html
<link rel="preload" href="MonaSansVF[wdth,wght,opsz,ital].woff2" as="font" type="font/woff2" crossorigin>
```

Or you can use one of the other variable font files, which cover small portions of the design space. For example, if you're only using the regular width weights and the italic styles, you can use the `MonaSansVF[wght,opsz,ital]` file instead.

## Stylistic sets

Mona Sans has eight stylistic sets:

| Set | Description | Example |
| --- | --- | --- | 
| ss01 | Square diacritical marks | ![ss01](https://github.com/user-attachments/assets/18fa3132-6839-4ef9-afd9-c75a082899ef) |
| ss02 | Wide uppercase I | ![ss02](https://github.com/user-attachments/assets/a0de7f9c-f9c0-4583-ac32-a10d25a54328) |
| ss03 | Lowercase l with tail | ![ss03](https://github.com/user-attachments/assets/8594effd-0528-4af9-8c58-0dfba66b2b45) |
| ss04 | Lowercase l with top serif | ![ss04](https://github.com/user-attachments/assets/7c7610a9-947e-45d5-80fc-71849a257d82) |
| ss05 | Double-storey a | ![ss05](https://github.com/user-attachments/assets/d31a11b8-1809-4a34-bbcb-b8b7057ddef0) |
| ss06 | Double-storey g | ![ss06](https://github.com/user-attachments/assets/ca8bef04-68d8-4c36-bfa6-8313d5642a9d) |
| ss07 | Square G | ![ss07](https://github.com/user-attachments/assets/4d5fb045-df90-4dc7-8dbb-3f2a271477df) |
| ss08 | Tabular zero with straight bar | ![ss08](https://github.com/user-attachments/assets/6c54f0eb-0054-4876-a366-1c00d955b89b) |
| ss09 | Q with diagonal arm | - |
| ss10 | J with bowl | - |

When using Mona Sans on the web, you can control each stylistic set with the syntax `"ssXX" on/off`. If you wanted square diacritical marks, small letter L distinct from capital I, and alternative small letter g it would look like this:

```css
html {
  font-family: 'Mona Sans VF';
  font-feature-settings: "ss01" on, "ss03" on, "ss05" on;
}
```

## Ligatures

Mona Sans comes with seven ligatures:

| Ligature | Example |
| --- | --- | 
| ff | ![ff](https://github.com/user-attachments/assets/257cf188-808c-4bfc-9087-61dedf4c1e6f) | 
| ffi | ![ffi](https://github.com/user-attachments/assets/f7c92ef1-90ef-4bec-9f00-1a4c522e1c73) | 
| fy | ![fy](https://github.com/user-attachments/assets/232ead1c-09bd-4567-b17f-9d2651edef63) | 
| fi | ![fi](https://github.com/user-attachments/assets/2cd901e4-f077-449d-ad6a-eec683b7f402) | 
| fl | ![fl](https://github.com/user-attachments/assets/c0591522-f273-48fd-a0f5-0e2c77df6e9a) | 
| ti | ![ti](https://github.com/user-attachments/assets/556aab9f-e8f5-40dd-b8d2-70903d0cab65) | 
| tt | ![tt](https://github.com/user-attachments/assets/d0392c30-2b8c-4646-b578-0ae66a328505) | 

## Mona Sans Styles

With the newly added monospace and display styles, Mona Sans’ design space now spans 128 instances. Below is a map for the whole space. Style entries with a hyphen are elidable, meaning they are the default and have no name.

| Axes | Mapping | Style name |
| --- | --- | --- |
| Weight (wght) | 200 | ExtraLight |
|  | 300 | Light |
| - | 400 | Regular |
| - | 500 | Medium |
| - | 600 | SemiBold |
| - | 700 | Bold |
| - | 800 | ExtraBold |
| - | 900 | Black |
| Width (wdth) | 75 | Condensed |
| - | 87.5 | SemiCondensed |
| - | 100 | - |
| - | 112.5 | SemiExpanded |
| - | 125 | Expanded |
| Italic (ital) | 0 | Roman |
| - | 1 | Italic |
| Optical Size (opsz) | 20 | - |
| - | 72 | Display |

### Mona Sans Monospace Styles

| Family or Axes | Mapping | Styles |
| --- | --- | --- |
| Weight (wght) | 200 | ExtraLight |
| - | 300 | Light |
| - | 400 | Regular |
| - | 500 | Medium |
| - | 600 | SemiBold |
| - | 700 | Bold |
| - | 800 | ExtraBold |
| - | 900 | Black |

## License
Mona Sans is licensed under the [SIL Open Font License v1.1](https://scripts.sil.org/OFL).
