# BB Blocks

A flexible model for ACF Gutenberg blocks in a theme.

## Structure

Each block is contained in its own directory with the following files. For example:

- ACF group: `bb-blocks/sample/group_65d71ddf065bb.json`
- block declaration: `bb-blocks/sample/block.json`
- stylesheet: `bb-blocks/sample/style.scss`
- render template: `bb-blocks/accordion/accordion.php`
- JS code: `bb-blocks/sample/sample.js`

Make sure to edit the files accordingly for new blocks.

## Usage

Add the `bb-blocks` directory to your theme and load the blocks with the following command in your `functions.php`:

```
require_once get_template_directory() . '/bb-blocks/init.php';
```

Check out the ACF Options page to set which blocks are to be loaded.

## SCSS

To include the blocks styles import it in your SCSS. Alternatively you could use the `gulp-sass-glob` node module and just glob the stylesheets:

```
/* BB Blocks */
@import '../../bb-blocks/**/style.scss';
```

## JS

Custom JS for the block needs to be manually imported in your main script.

## Config

An ACF options page should appear in the backend where you can choose which BB blocks and WordPress blocks to load.

## Editing ACF groups

For easier editing of ACF group I recommend symlinking the block's JSON into the `acf-json/` directory of the theme. The group will appear in the ACF interface, ready for import, and any changes will be reflected in the block's JSON. Once you're done editing you can remove the symlink.

```
$ ln -s bb-blocks/sample/group_65d71ddf065bb.json acf-json/
```
