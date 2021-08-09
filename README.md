# house-inventory-client

## Summary
1. The app solves the problem of household inventory manage by providing critical information, reminders, and analysis to help modern families to
    1. Understand assets and inventories at house
    1. Reduce waste on unnecssary items
    1. Overpurchase on certain products
    1. Understand household consumptions
    1. Prevent waste by product expiration
    1. Tracking on family expenditure and household expense
    1. Get latest promotions on discounts from sellers
    1. Locate goods in a house
1. On business side sellers can
    1. Promote to users with marketing campaign
    1. Analysis on user behavior

## Features and functions
1. Manage family members in a house
1. List of groceries in a house
1. Records of purchases, including price, amount, deals, and location
1. Reminders to finishing or expiring products
1. Reminders to deals and discount

## Features on Technology
1. Login/Register with local or OAuth by LINE or Google. 
1. Web Socket to ensure members in the same house get updated with latest data.
1. Scan barcode or QRcode to check or register products.
1. Map view to check nearest sellers or from where a product was purchased.
1. IoT technology to locate goods in house with integration with smart devices. (Bluetooth, Wi-Fi, NFC)

## 

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).


### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).
