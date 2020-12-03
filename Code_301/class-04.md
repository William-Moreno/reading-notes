# Resoponsive Web Design and Regular Expressions

---

# CSS Grid

CSS grid has made creating two dimensional layouts easier. It allows us to arrange elements in multiple colums and rows. CSS grid gives us control the minimum and maximum widths of grid 'cells'. This makes it possible to exert control of their aspect ratio as the size of the viewport changes.

## Grid Properties

### Parent Properties

- **display** defines the element as a grid and creates a context for formatting content as a grid

- **grid-template-columns** allows us to define the size of each column in the grid. Values can be given in pixels, percentages and fractions of free space. Additionally, we can assign names to the lines between the "spaces". If we do not designate names for the lines they will arbitrarily be assigned a nummerical designation.

- **grid-template-rows** allows us to define the size of each row in the grid. Values can be given in pixels, percentages and fractions of free space. Additionally, we can assign names to the lines between the "spaces". If we do not designate names for the lines they will arbitrarily be assigned a nummerical designation.

- **grid-template-area** assigns and defines names for grid template areas for later reference and use. If the same neame is used in mutiple cells the content applied to that name will span the cells.

- **grid-template** - combines grid-template-columns/rows/areas into a single line shorthand.

- **column-gap, row-gap, _grid-column-gap, grid-row-gap_** these specify the sizes of grid lines and allow us to set the width of the 'gutters' between rows and columns.

- **gap, _grid-gap_** a shorthand method for column-gap and row-gap.

- **justify-items** aligns items along the x-axis of the grid.

- **align-items** aligns items along the y-axis of the grid.

- **place-items** is shorthand for align-items and justify-items. values should be entered first for align-items, a forward slash and the for justify-items.

- **justify-content** aligns our grid along the x-axis of the grid when it is smaller than our actual grid container.

- **align-content** aligns our grid along the y-axis of the grid when it is smaller than our actual grid container.

- **place-content** is shorthand for align-content and justify-content. values should be entered first for align-content, a forward slash and the for justify-content.

### Children Properties

- **grid-column-start, grid-column-end** determine an items location within the grid by designating the line at which the item begins and the line at which it ends.

- **grid-row-start, grid-row-end** determine an items location within the grid by designating the line at which the item begins and the line at which it ends.

- **grid-column, grid-row** these are shorthands for the pairs above.

- **grid-area** allows us to combine all four of these designators into a single line, and can also be used in conjunction with `grid-template-areas`.

- **justify-self** aligns the item inside its grid cell along the x-axis.

- **align-self** aligns the item inside its grid cell along the y-axis.

- **place-self** is shorthand for align-self and justify-self. values should be entered first for align-self, a forward slash and the for justify-self.

[Back to Main](../README.md)
