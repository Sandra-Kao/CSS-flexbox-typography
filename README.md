# CSS-flexbox-typography

Please see codepen:
https://codepen.io/K-SY/pen/XWMWRyz?editors=1100


``` scss
:root {
  --width-max: 140rem;
  --margin-h: 3rem;
  --margin-v: 5rem;
}

@mixin clearfix {
  &::after {
    content: "";
    clear: both;
    display: table;
  }
}

@mixin baseCol {
  background: var(--color-orange-lighten);
  flex: auto;
  padding: 1rem;
  &:not(:last-child) {
    margin-right: var(--margin-h);
  }
}

@mixin RWD-800-flex($flex) {
  @media (max-width: 800px) {
    margin: var(--margin-h);
    flex: $flex;
  }
}

.grid-test {
  padding: 4rem;
  @include clearfix;

  .row {
    border-radius: 30px;
    background: #1a82ad1c;
    max-width: var(--width-max);
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin: 0 auto;
    &:not(:last-child) {
      margin-bottom: var(--margin-v);
    }

    .col-1-of-2 {
      @include baseCol;
      @include RWD-800-flex(2);
    }

    .col-1-of-3 {
      max-width: calc((100% - var(--margin-h) * 2) / 3);
      @include baseCol;
      @include RWD-800-flex(2);
    }

    .col-2-of-3 {
      @include baseCol;
      @include RWD-800-flex(3);
    }

    .col-1-of-4 {
      max-width: calc((100% - var(--margin-h) * 3) / 4);
      @include baseCol;
      @include RWD-800-flex(2);
    }

    .col-2-of-4 {
      @include baseCol;
      @include RWD-800-flex(4);
    }

    .col-3-of-4 {
      @include baseCol;
      @include RWD-800-flex(3);
    }
  }
}

```
