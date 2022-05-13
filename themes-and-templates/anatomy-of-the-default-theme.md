# Anatomy of the default theme

### Standard layout

|              |   |   |
| ------------ | - | - |
|              |   |   |
| Page Content |   |   |
|              |   |   |

#### Body

```
```

" class="<{$xoops\_langcode}>"> <{if $xoBlocks.canvas\_left and $xoBlocks.canvas\_right}> <{assign var=columns\_layout value='threecolumns-layout'}> <{elseif $xoBlocks.canvas\_left}> <{assign var=columns\_layout value='leftcolumn-layout'}> <{elseif $xoBlocks.canvas\_right}> <{assign var=columns\_layout value='rightcolumn-layout'}> <{/if}>

<{if $columns\_layout}> class="<{$columns\_layout}>"<{/if}>>

#### Header

This is the topmost portion of your page - your logo, banner and banner ads show here.

```
```



<{$xoops\_banner}>

#### Header Menu

Just below your main header, there is a place for additional links you may want on your pages. Customize this area to place the links here that you want.

```
```

#### Page Content

Here you have the middle portion of your page - the left column, the center column and the right column are the 3 main areas.

```
```

**Left Column**

You can determine which blocks appear in each column in the administration area.

```
	<{if $xoBlocks.canvas_left}>
	<{includeq file="$theme_name/blockszone.html" blocks=$xoBlocks.canvas_left
		zoneClass='xo-canvas-column' zoneId='xo-canvas-leftcolumn'
	}>
	<{/if}>
```

**Center Column**

The center column has 3 zones - the top zone, the content zone and the bottom zone. The top and bottom zones will hold the blocks assigned to them and the content zone will display the content generated by the modules.

```
```

<{if $xoBlocks.page\_topleft or $xoBlocks.page\_topcenter or $xoBlocks.page\_topright}>

<{includeq file="$theme\_name/centerblocks.html" topbottom=top lcr=$theme\_top\_order|substr:0:1}> <{includeq file="$theme\_name/centerblocks.html" topbottom=top lcr=$theme\_top\_order|substr:1:1}> <{includeq file="$theme\_name/centerblocks.html" topbottom=top lcr=$theme\_top\_order|substr:2:1}>

<{/if}>

**Module Content**

```
	<{if $xoops_contents}>
	
```

<{$xoops\_contents}>

<{/if}>

**Bottom Blocks**

```
	<{if $xoBlocks.page_bottomleft or $xoBlocks.page_bottomcenter or $xoBlocks.page_bottomright}>
```

<{includeq file="$theme\_name/centerblocks.html" topbottom=bottom lcr=$theme\_bottom\_order|substr:0:1}> <{includeq file="$theme\_name/centerblocks.html" topbottom=bottom lcr=$theme\_bottom\_order|substr:1:1}> <{includeq file="$theme\_name/centerblocks.html" topbottom=bottom lcr=$theme\_bottom\_order|substr:2:1}>

<{/if}>

**Right Column**

The right column is another area for blocks to display.

```
	<{if $xoBlocks.canvas_right}>
	<{includeq file="$theme_name/blockszone.html" blocks=$xoBlocks.canvas_right
		zoneClass='xo-canvas-column' zoneId='xo-canvas-rightcolumn'
	}>
	<{/if}>
```

### Footer

This is the bottom of the page - if you put <{$xoops\_footer}> in this area, the footer you configured in the administration area will display here, or you can code your footer directly.

```
```
