# Custom Grid
Custom Grid is customise version of bootstrap grid where this is available with Multiple Grid column, multiple gutter width for respective multiple breakpoints.

# Usage of function

/*Example to call sass function to 
create container or row  or columns 
with respect to different breakpoints */

```
.newfluidcontainer {
  @include make-container();
}
.newcontainer {
  @include make-container();
  @include make-container-max-widths();
}
.newrow {
  @include make-row();
}
.newclass {
  @include make-col-ready();
  @include make-column(2, xs);
  @include make-col-offset(1, 4);
  @include media-breakpoint-down(xs) {
      margin-top: 32px;
  }
  @include media-breakpoint-up(sm) {
      @include make-column(4, sm);
      @include make-col-offset(0, 8);
  }
}
```