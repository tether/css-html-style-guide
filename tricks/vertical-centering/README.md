# Vertical centering

Here's some examples of how to center horizontally and vertically a div inside the body of your document.

## Using table

  > Pretty neat but doesn't fit to every use case.

```css
  html {
    display: table;
    table-layout: fixed;
    width: 100%; 
    height: 100%;
  }

  body {  
    display: table-cell;  
    width: 100%; 
    height: 100%;
    vertical-align: middle;
    margin:0;
  }

  .vertical {
    width: 50%;
    margin: auto;
  }
```

## Using flexbox

  > From far the best solution but is not supported by all browsers.

```css
  html, body {
    height:100%;
  }
  body{
    display:-webkit-flex;
    display:flex;

    -webkit-align-items: center;
    align-items: center;
  }

  .vertical {
    margin:0 auto;
  }
```

## Using position absolute and negative margin

  > if you don't want to use display table. It requires to change the margin left and top of the container when its size change (not really maintainable hey :s) 

see this [article](http://coding.smashingmagazine.com/2013/08/09/absolute-horizontal-vertical-centering-css/)

```css
  .vertical {
    width: 300px;
    height: 300px;
    padding:20px;
    position: absolute;
    top: 50%; left: 50%;
    margin-left: -170px; /* (width + padding)/2 */
    margin-top: -170px; /* (width + padding)/2 */
  }

```