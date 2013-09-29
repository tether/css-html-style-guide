# Sticky footer

In this example, the ancestor class `wrapper` can be the body itself or whatever markup you want. The most important is to have the ancestor displayed as a table:

```css
  display : table;
  height: 100%;
  width:100%;
  behavior: url(display-table.min.htc);
```
  > the behavior attribute is for IE7

and the footer displayed as a table row:

```css
  display : table-row;
  height: 100px;
```
  > height is mandatory