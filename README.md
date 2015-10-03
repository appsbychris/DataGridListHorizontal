# DataGridListHorizontal
`HorizontalGridDelegate` for enyojs 2.5, and a fix to `DataGridList.js`

So, it seems there was never a `HorizontalGridDelegate` made.

I needed a layout that laid it out in a grid, in columns, and would continue horizontally with no vertical scroll.

So i did a quick copy/paste of the `VerticalGridDelegate` and changed a few functions.

And then i tried to use it by setting `orientation: "horizontal"` on my `DataGridList`.
It kept defaulting to `vertical`.

Root cause was it was checking `this.orientation` in the `constructor` function, where user supplied properties aren't added until it gets to `enyo.Object`.

So I changed `constructor` to `create`, and then it worked.


I will be refining the `delegate` as i continue with this project and get some of the sizing kinks worked out.
