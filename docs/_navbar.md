<button type="button" onclick="switch_style('blue');return false;" name="theme" value="Blue Theme" id="blue">Blue Theme</button>
<button type="button" onclick="switch_style('pink');return false;" name="theme" value="Pink Theme" id="pink">Pink Theme</button>













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
  <li>
    <!-- Rounded switch -->
    <label class="switch">
      <input type="checkbox" onclick="myFunction()">
      <span class="slider round"></span>
    </label>
  </li>
  <li>Cosmoglobe Website</li>
  <li>BeyondPlanck Website</li>
</ul>

<button onclick="myFunction()">Toggle dark mode</button>
<style>
.dark-mode {
  background-color: black;
  color: white;
}
 </style>

<script>
function myFunction() {
   //var element = document.body;
   var element = Docsify.dom;
   element.classList.toggle("dark-mode");
}
</script>

<style>
 .demo-theme-preview a {
    padding-right: 10px;
 }

 .demo-theme-preview a:hover {
    cursor: pointer;
    text-decoration: underline;
 }
</style>

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

<style>
 /* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

/* Hide default HTML checkbox */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* The slider */
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: .4s;
  transition: .4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}

input:checked + .slider {
  background-color: #2196F3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196F3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
} 
</style>
