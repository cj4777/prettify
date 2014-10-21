Prettify
========

We use this on [blog.yujinrobot.com](http://blog.yujinrobot.com).

Template Configuration
----------------------

Doesn't play very well with dynamic views, need some magic to get that to work. In the template, just before ```</head>```:

```
    <!--<link href='//cdnjs.cloudflare.com/ajax/libs/prettify/r298/prettify.min.css' rel='stylesheet'/>-->
    <link href='https://raw.githubusercontent.com/yujinrobot/prettify/master/prettify.min.css' rel='stylesheet'/>

    <script src='//cdnjs.cloudflare.com/ajax/libs/prettify/r298/prettify.min.js'/>
    <!--<script src='https://raw.githubusercontent.com/yujinrobot/prettify/master/prettify.min.js'/>-->

    <!--<script src='https://raw.githubusercontent.com/yujinrobot/prettify/master/run_prettify.js'/>-->
    <script src='//cdnjs.cloudflare.com/ajax/libs/prettify/r298/run_prettify.js'/>
    <script>
      $(window.blogger.ui()).on(&#39;viewitem&#39;, function (event, post, element) {
        element.each(function () {
          prettyPrint(null, this);
        });
      });
    </script>
```

**Q:** This isn't working linking the js back to our site here on github (note files.yujinrobot.com does not work either). There is some magic in the cloudfare linkage.

Usage
-----

* Use ```<pre>``` around blocks of code
* Use ```<code>``` around inline code.
* Any angle brackets need html representations.
* Add directly to the html, e.g.

```
<pre class="prettyprint lang-c++">
#include &lt;iostream&gt;

int main() {
    std::cout &lt;&lt; "Hello Dude" &lt;&lt; std::endl;
    return 0;
}
</pre>

```
