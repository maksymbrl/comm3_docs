<ul>
  <li>Themes
    <ul>
      <li><a data-theme="vue">vue</a></li>
      <li><a data-theme="buble">buble</a></li>
      <li><a data-theme="dark">dark</a></li>
      <li><a data-theme="pure">pure</a></li>
    </ul>
  </li>
  <li>Another element</li>
</ul>

* [Cosmoglobe Website](https://www.cosmoglobe.uio.no/)
* [BeyondPlanck Website](https://beyondplanck.science)


<script>
  var preview = Docsify.dom.find('.demo-theme-preview');
  var themes = Docsify.dom.findAll('[rel="stylesheet"]');

  preview.onclick = function (e) {
     var title = e.target.getAttribute('data-theme');

     themes.forEach(function (theme) {
        theme.disabled = theme.title !== title;
     });
  };
</script>
