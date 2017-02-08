# Stock Vue.js with Bootstrap SASS 3

### Clone and play around with Vue.js + Bootstrap 3

``` bash
# clone this repo

# install node if you haven't yet
brew install node

# get into the directory of this app and install dependencies
npm install --global vue-cli
npm install

# start server
npm run dev

```

### Now, you want to build your own app from the ground up?

``` bash
# Here's how I did everything.
# Install Vue.js
npm install --global vue-cli

# Initialize your project, answer questions
vue init webpack my-vue-project

# Install dependancies
cd my-vue-project
npm install
npm install node-sass --save-dev
npm install sass-loader --save-dev
npm install pug --save-dev
npm install bootstrap-sass --save-dev
npm install vue-strap --save-dev
npm run dev

# Setup your app.scss file as a stylesheet manifest
mkdir src/assets/styles && touch src/assets/styles/app.scss

# Duplicate and comment out bootstrap variables for easy overriding
awk '{print "//" $0}' node_modules/bootstrap-sass/assets/stylesheets/bootstrap/_variables.scss > src/assets/styles/bootstrap-variable-overrides.scss

# Import app.scss in the file `App.vue` by pasting the following code
<style lang="scss">
  @import './assets/styles/app.scss';
</style>

# In your .vue files you may use pug for html pre-processing
<template lang="pug">…</template>

# Set up app.scss
$icon-font-path: "~bootstrap-sass/assets/fonts/bootstrap/";
@import '~bootstrap-sass/assets/stylesheets/_bootstrap.scss';
@import 'bootstrap-variable-overrides';
@import '~bootstrap-sass/assets/stylesheets/bootstrap/variables';
@import '~bootstrap-sass/assets/stylesheets/bootstrap/mixins';
@import 'overrides';
```

Done.