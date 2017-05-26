View `jsraings.html` for an example implenetation :)

Straightforward enough, for the <i>most</i> basic behaviour use :

```
<form>
<div>
  <ul class="feedback_icons">
    <li x-score="1"><span>Rating 1</span></li>
    <li x-score="2"><span>Rating 2</span></li>
    <li x-score="3"><span>Rating 3</span></li>
  </ul>
</div>
</form>
```

`x-score` is the value of the rating. The span inside the li tag is used to apply classes for styling/icons. by default, the glyphicon's  `glyphicon glyphicon-star` and `glyphicon glyphicon-star-empty` are used. But can be chaned using `on_class` and `off_class` in the config you pass.

If you want to add comments, simply use :

```
<form>
<div>
  <input type="hidden" name="rating" class="rating">
  <ul class="feedback_icons">
    <li x-score="1"><span>Rating 1</span></li>
    <li x-score="2"><span>Rating 2</span></li>
    <li x-score="3"><span>Rating 3</span></li>
  </ul>
  <div class="feedback_comment_container">
    <textarea></textarea>
  </div>
</div>
</form>
```

Pass the following object to config and initalize.

```
{
  feedback_bar : "feedback_bar",
  deafault_score : 5,
  output : "rating",
  comment_bar : {
    container : "feedback_comment_container",
    always_visible : false,
    open_on : 3
  },
  on_class "someicon",
  off_class "someicon_off"
}
```

<ul>
  <li>`feedback_bar` - the class name of the ul, containing the feedback symbols themselves (REQURIED)</li>
  <li>`deafault_score` - the inital score of the bar (OPTIONAL - default value of 4)</li>
  <li>`output` - the class name of an `<input>` tag, to write the selected rating's `x-score` attribute to on update (OPTIONAL)</li>
  <li>`comment_bar` - (OPTIONAL)
    <ul>
      <li>`container` - A container for the comment box + associated elements (REQUIRED, with comment_bar)</li>
      <li>`always_visible` - if true, the comment box will always be visible (OPTIONAL, default false)</li>
      <li>`open_on` - if star rating equal to or lower, the comment box will open up (OPTIONAL, default 4)</li>
    </ul>
  </li>
  <li>`on_class` - the class name that willbe appended to the `<span>` of the pinned ratings i.e. `glyphicon glyphicon-star` (OPTIONAL)</li>
  <li>`off_class` - the class name that willbe appended to `<span>` of the non-pinned ratings i.e `glyphicon glyphicon-star-empty`(OPTIONAL)</li>
</ul>
