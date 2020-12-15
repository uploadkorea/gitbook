# Flex

```css
.inner-group {background: #ccc; padding: 0 16px; display: flex; flex-wrap: wrap; margin: 0 auto -16px; position: relative; overflow: hidden; }
.inner-group .inner { display: flex; flex: 0 0 33.33%; min-width: calc(33% - 8px); padding-top: 16px; padding-bottom: 0; margin-bottom: 16px; position: relative; }
.inner-group .inner .inner-box { width: 100%; margin-right: 16px; background: #eee; border-radius: 8px; padding: 1rem; box-sizing: border-box; width: 100%; }
.inner-group .inner .inner-box::after { position: absolute; content: ''; width: 1px; height: calc(100% - 16px); background: #000; right: 8px; top: 16px; }
.inner-group .inner:nth-child(3n) .inner-box { margin-right: 0; }
.inner-group .inner:nth-child(3n) .inner-box::after { display: none; }
.inner-group .inner::before { content: ''; display: block; width: 100%; height: 1px; position: absolute; left: 0; bottom: -17px; background: #000; }
.inner-group .inner:last-child .inner-box::after {display: none;}

@media screen and (max-width:1023px) {
  .inner-group .inner { min-width: calc(50% - 8px); margin-right: 0; flex: 0 0 50%; }
  .inner-group .inner:nth-child(2n) .inner-box { margin-right: unset; }
  .inner-group .inner:nth-child(2n) .inner-box::after { display: none; }
  .inner-group .inner:nth-child(2n):last-child { margin-right: 0; }
  .inner-group .inner:nth-child(odd) .inner-box { margin-right: 16px; }
  .inner-group .inner:nth-child(odd) .inner-box::after { display: block; }
  .inner-group .inner:last-child .inner-box::after {display: none;}
  .inner-group .inner:last-child::before { display: none; }
}

@media screen and (max-width:723px) {
  .inner-group .inner { width: 100%; flex: 1 auto; }
  .inner-group .inner:nth-child(1n) .inner-box { margin-right: 0; }
  .inner-group .inner:nth-child(1n) .inner-box::after { display: none; }
}
```

```markup
<div class="inner-group">
    <div class="inner"><div class="inner-box">1</div></div>
    <div class="inner"><div class="inner-box">2</div></div>
    <div class="inner"><div class="inner-box">3</div></div>
    <div class="inner"><div class="inner-box">4</div></div>
    <div class="inner"><div class="inner-box">5</div></div>
    <div class="inner"><div class="inner-box">6</div></div>
</div>
```



