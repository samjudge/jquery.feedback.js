View `jsraings.html` for an example implenetation :)

Straightforward enough, for the <i>most</i> basic behaviour use :

```
<form>
<div>
  <ul class="feedback_icons">
    <li x-score="1">Rating 1</li>
    <li x-score="2">Rating 2</li>
    <li x-score="3">Rating 3</li>
  </ul>
</div>
</form>
```

`x-score` is the value of the rating.

If you want to add comments, simply use :

```
<form>
<div>
  <input type="hidden" name="rating" class="rating">
  <ul class="feedback_icons">
    <li x-score="1">Rating 1</li>
    <li x-score="2">Rating 2</li>
    <li x-score="3">Rating 3</li>
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
  }
}
```

<ul>
  <li>`feedback_bar` - the class name of the ul, containing the feedback symbols themselves (REQURIED)</li>
  <li>`deafault_score` - the inital score of the bar (OPTIONAL - default value of 4)</li>
  <li>`output` - the class name of an `<input>` tag, to write the selected rating's `x-score` attribute to on update</li>
  <li>`comment_bar` - (OPTIONAL)
    <ul>
      <li>`container` - A container for the comment box + associated elements (REQUIRED, with comment_bar)</li>
      <li>`always_visible` - if true, the comment box will always be visible (OPTIONAL, default false)</li>
      <li>`open_on` - if star rating equal to or lower, the comment box will open up (OPTIONAL, default 4)</li>
    </ul>
  </li>
</ul>
