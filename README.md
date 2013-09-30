# [PetroFeed](http://petrofeed.com) CSS + HTML Style Guide

> A minimal HTML and CSS style guide to produce decoupled markup and styles.

## <a name='TOC'>Table of Contents</a>

  1. [Selectors](#selectors)
  1. [Variables](#variables)
  1. [Mixins](#mixins)
  1. [Blocks](#blocks)
  1. [Comments](#comments)
  1. [Whitespace](#whitespace)
  1. [Naming Conventions](#naming)
  1. [Data Attributes](#data)
  1. [Browser Compatibility](#compatibility)
  1. [Testing](#testing)
  1. [Performance](#performance)
  1. [Resources](#resources)

## <a name='selectors'>Selectors</a>

  - Selectors should be as broad as possible. Really specific selectors are unnecessary and hinder performance.

    ```less

    // bad
    ul > li > a {
      color: blue;
    }

    // good
    a.nav {
      color: blue;
    }
    
    ```

    **[[⬆]](#TOC)**

## <a name='variables'>Variables</a>

  - Use variables to declare constants like
      - colours
      - font-sizing
      - column widths
      - other fixed sizes

    ```less
    
    @small = 12px;
    @medium = 16px;
    @large = 24px;
    @red = #CE6060;

    ```

  - Wrap your variables in classes so that they can easily be managed

    ```less
    
    .small {
      font-size: @small;
    }

    .medium {
      font-size: @medium;
    }

    .large {
      font-size: @large;
    }

    ```

  **[[⬆]](#TOC)**

## <a name='mixins'>Mixins</a>

  - Use mixins where applicable
  - More coming....

  **[[⬆]](#TOC)**

## <a name='blocks'>Blocks</a>

  - Use multi-line blocks to make CSS cleaner and easier to read
  
    ```less

    // bad
    ul > li > a { color: red; }

    // good
    a.nav {
      color: red;
    }

    ```

  - Group similar style declarations together (ie. positioning, sizing, coloring, etc.)

    ```less

    // bad
    a.nav {
      margin: 5px;
      font-size: 20px;
      postion: absolute;
      color: @red;
      padding: 3px;
      top: 0;
      left: 10px;
    }

    // good
    a.nav {
      postion: absolute;
      top: 0;
      left: 10px;
      margin: 5px;
      padding: 3px;
      font-size: 20px;
      color: @red;
    }

    ```

  **[[⬆]](#TOC)**

## <a name='comments'>Comments</a>

  - Use comments :smile:
  - More coming....

  **[[⬆]](#TOC)**

## <a name='whitespace'>Whitespace</a>

  - Whitespace is nice to have
  
    ```less

    // bad
    ul > li > a{
      color: red;
    }
    .some-class{
      background: purple;
    }

    // good
    a.nav {
      color: red;
    }

    .some-class {
      background: purple;
    }

    ```

  **[[⬆]](#TOC)**

## <a name='naming'>Naming Conventions</a>

  - Coming...

  **[[⬆]](#TOC)**

## <a name='data'>Data Attributes</a>

  - Use data attributes for data not for selectors. That's what classes and id's are for and they are faster. (TODO: Find Perf)
  - More Coming...

  **[[⬆]](#TOC)**

## <a name='compatibility'>Browser Compatibility</a>

  - Coming...

  **[[⬆]](#TOC)**

## <a name='testing'>Testing</a>

  - Coming... needs more research

  **[[⬆]](#TOC)**

## <a name='performance'>Performance</a>

  - Coming...

  **[[⬆]](#TOC)**

## <a name='resources'>Resources</a>

  - [Decoupling your HTML, CSS, and JavaScript](http://philipwalton.com/articles/decoupling-html-css-and-javascript/) - Philip Walton
  - [Decouple Your CSS From HTML With Reusable Modules](http://thenittygritty.co/decouple-css) - Hans Christian Reinl
  - [Front-end Code Standards & Best Practices](http://isobar-idev.github.io/code-standards/) - Isobar iDev

  **[[⬆]](#TOC)**
