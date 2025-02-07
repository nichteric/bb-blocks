# BB Blocks

A flexible model for ACF Gutenberg blocks in a theme

## Structure

Each block is contained in its own directory with the following files:

- ACF group: `bb-blocks/sample/group_65d71ddf065bb.json`
- block declaration: `bb-blocks/sample/block.json`
- Stylesheet: `bb-blocks/sample/style.scss`
- Render template: `bb-blocks/accordion/accordion.php`
- JS code: `bb-blocks/sample/sample.js`

## Usage

Add the `bb-blocks` directory to your theme and load the blocks with the following command in your `functions.php`:

```
require_once get_template_directory() . '/bb-blocks/init.php';
```

Check out the ACF Options page to set which blocks are to be loaded.

## SCSS

To include the blocks SCSS add the node-module `gulp-sass-glob` to the project and insert the following line in your SCSS stylesheet:

```
/* BB Blocks */
@import '../../bb-blocks/**/style.scss';
```

## JS

Custom JS for the block needs to be manually imported in your main script.

## Config

An ACF options page should appear in the backend where you can choose which BB blocks and WordPress blocks to load.
