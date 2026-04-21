# Photography by Andrew Webb

[photography.drewbefree.com](https://photography.drewbefree.com)

## Adding Photos

### Section galleries (Boogiesnaps, Drew's Doggies, Weddings)

1. Drop your image files into the matching folder:
   - `images/boogiesnaps/`
   - `images/doggies/`
   - `images/weddings/`

2. Open `index.html` and find the `galleries` object near the bottom in the `<script>` block. Add an entry for each photo:

```js
const galleries = {
  boogiesnaps: [
    { src: 'images/boogiesnaps/photo1.jpg', caption: 'Optional caption' },
    { src: 'images/boogiesnaps/photo2.jpg', caption: '' },
  ],
  ...
};
```

### Home page ticker

1. Drop image files into `images/ticker/`

2. In `index.html`, find the `ticker` array and add the paths:

```js
const ticker = [
  'images/ticker/photo1.jpg',
  'images/ticker/photo2.jpg',
  'images/ticker/photo3.jpg',
  'images/ticker/photo4.jpg',
  'images/ticker/photo5.jpg',
];
```

The ticker auto-scrolls and loops. It stays hidden until at least one image is added.

### Home page card covers

Each section card on the home page can have a cover photo. In `index.html`, find the `homeCards` array and fill in the `cover` path:

```js
const homeCards = [
  { key: 'boogiesnaps', title: 'Boogiesnaps',    desc: '...', cover: 'images/boogiesnaps/cover.jpg' },
  { key: 'doggies',     title: "Drew's Doggies", desc: '...', cover: 'images/doggies/cover.jpg'     },
  { key: 'weddings',    title: 'Weddings',        desc: '...', cover: 'images/weddings/cover.jpg'    },
];
```

## Deploying

After adding images and updating `index.html`, commit and push:

```bash
git add .
git commit -m "Add photos"
git push
```

GitHub Pages will update the live site automatically within a minute or two.
