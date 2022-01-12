<h2 align='center'><samp>vite-plugin-image-presets</samp></h2>

<p align='center'>Image Presets for Vite.js apps</p>

<p align='center'>
  <a href='https://www.npmjs.com/package/vite-plugin-image-presets'>
    <img src='https://img.shields.io/npm/v/vite-plugin-image-presets?color=222&style=flat-square'>
  </a>
  <a href='https://github.com/ElMassimo/vite-plugin-image-presets/blob/main/LICENSE.txt'>
    <img src='https://img.shields.io/badge/license-MIT-blue.svg'>
  </a>
</p>

<br>

[Vite]: https://vitejs.dev/
[Sharp]: https://sharp.pixelplumbing.com/
[îles]: https://iles-docs.netlify.app/
[example]: https://github.com/ElMassimo/vite-plugin-image-presets/blob/main/example/App.vue#L10

This [Vite] plugin allows you to define presets for image processing using [Sharp],
allowing you to optimize, resize, and process images consistently and with ease.

## Installation 💿

```bash
npm install -D vite-plugin-image-presets # pnpm, yarn
```

## Usage 🚀

Add it to your plugins in `vite.config.ts`

```ts
import { defineConfig } from 'vite'
import imagePresets, { widthPreset } from 'vite-plugin-image-presets' 

export default defineConfig({
  plugins: [
    imagePresets({
      thumbnail: widthPreset({
        class: 'thumbnail',
        loading: 'lazy',
        widths: [48, 96],
        formats: {
          webp: { quality: 50 },
          jpg: { quality: 70 },
        },
      }),
    }),
  ],
})
```

For example, this preset will be used whenever an image URL has `?preset=thumbnail`:

```js
import thumbnails from '~/images/logo.jpg?preset=thumbnail'
```

Check the [example] for additional usage information.

More documentation coming soon, in [îles].

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).