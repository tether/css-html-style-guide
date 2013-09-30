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
  1. [Modularity](#modularity)
  1. [Browser Compatibility](#compatibility)
  1. [Testing](#testing)
  1. [Performance](#performance)
  1. [Resources](#resources)

## <a name='selectors'>Selectors</a>

  - Selectors are evaluated **right to left** and should be as broad as possible. Really specific selectors are unnecessary and hinder performance. See [Selector Performance](http://smacss.com/book/selectors).

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
      - other fixed sizes (ie. footer height)

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

  - Use mixins where applicable to keep things consistent and prevent forgotten vendor specific style declarations.
  
    ```less
    // bad
    a.nav {
      -webkit-border-radius: 2px;
      -moz-border-radius: 2px;
      border-radius: 2px;
    }

    // good
    li.nav {
      .rounded(2px);
    }
    ```

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

  - Put  before and after each style block.
  
    ```less
    // bad
    ul > li > a{
      color: @red;
    }
    .some-class{
      background: @purple;
    }

    // good
    a.nav {
      color: @red;
    }

    .some-class {
      background: @purple;
    }
    ```

  **[[⬆]](#TOC)**

## <a name='naming'>Naming Conventions</a>

  - Use meaningful class and id names

    ```less
    // bad
    .l1 {
      color: @red;
    }

    // good
    .link.first {
      color: @red;
    }
    ```

  - Use multiple classes instead of single monster sized ones. You can get the same effect out of more selectors but you also get additional flexibility.

    ```less
    // bad
    .btn-large-success {
      width: @btn-large-width;
      height: @btn-large-height;
      background: @blue;
    }

    // good
    .btn.large.success {
      width: @btn-large-width;
      height: @btn-large-height;
      background: @blue;
    }
    ```

  **[[⬆]](#TOC)**

## <a name='data'>Data Attributes</a>

  - Use data attributes for data not for selectors. That's what classes and id's are for and they are faster. [Perf Test](http://jsperf.com/class-vs-data-attribute-selector-performance)
  
    ```less
    // bad
    [data-role="page"] {
      height: 100%;
    }

    // good
    .page {
      height: 100%;
    }
    ```

  **[[⬆]](#TOC)**

## <a name='modularity'>Modularity</a>

  - Separate your CSS (LESS) files into one file per section with a folder structure like so:

    ```
      common
        -> common.less
        -> reset.less
        -> variables.less
        -> layouts.less
      public
        -> public.less
        -> login.less
        -> home.less
      base.less
    ```

  - `@import` the other files that you need.

    ```less
      // in base.less
      @import 'common/common.less';
      @import 'public/public.less';

      // in common.less
      @import 'variables.less';
      @import 'layouts.less';

      // in public.less
      @import 'home.less';
      @import 'login.less';
    ```

  - Namespace each file so that you don't run into conflicts.

    ```less
      // in home.less

      // bad
      a.hero {
        background: @purple;
      }

      // good
      #home {
        a.hero {
          background: @purple;
        }
      }
    ```    

  **[[⬆]](#TOC)**

## <a name='compatibility'>Browser Compatibility</a>

  - Major IE9 issues:
      - A CSS stylesheet may contain up to a **maximum 4095 rules** [Telerik Tests](http://blogs.telerik.com/aspnet-ajax/posts/10-05-03/internet-explorer-css-limits.aspx)
      - A stylesheet may `@import` up to a **maximum of 31 other sheets**
      - `@import` nesting supports up to a **maximum of 4 levels deep**

  - For additional cross browser issues and solutions refer to [Browser Hacks](http://browserhacks.com/)

  **[[⬆]](#TOC)**

## <a name='testing'>Testing</a>

  - Coming... needs more research

  **[[⬆]](#TOC)**

## <a name='performance'>Performance</a>

  - Coming...

  **[[⬆]](#TOC)**

## <a name='resources'>Resources</a>

  - [Decoupling your HTML, CSS, and JavaScript](http://philipwalton.com/articles/decoupling-html-css-and-javascript/) - Philip Walton
  - [Writing Efficient CSS Selectors](http://csswizardry.com/2011/09/writing-efficient-css-selectors/) - Harry Roberts
  - [Decouple Your CSS From HTML With Reusable Modules](http://thenittygritty.co/decouple-css) - Hans Christian Reinl
  - [Front-end Code Standards & Best Practices](http://isobar-idev.github.io/code-standards/) - Isobar iDev
  - [30 CSS Best Practices for Beginners](http://net.tutsplus.com/tutorials/html-css-techniques/30-css-best-practices-for-beginners/) - Glen Stansberry

  **[[⬆]](#TOC)**
