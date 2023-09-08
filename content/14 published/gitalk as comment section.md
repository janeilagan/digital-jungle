---
alias:
tags:
- published
- index/00.01
---



Source: [gitalk/gitalk: Gitalk is a modern comment component based on Github Issue and Preact.](https://github.com/gitalk/gitalk)

If site is running on quartz/ hugo, make couple updates on the html layout files.

Load up gitalk stylesheet and js file inside [head.html](https://github.com/janeilagan/quartz/blob/digital-garden/layouts/partials/head.html) (line 41,42)
```html
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.css">
  <script src="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.min.js"></script>
```

Load up gitalk renderer inside [head.html](https://github.com/janeilagan/quartz/blob/digital-garden/layouts/partials/head.html) (line 194-204)
```html
 <script>
    const gitalk = new Gitalk({
       clientID: '{{ $.Site.Data.config.clientID }}',
       clientSecret: '{{ $.Site.Data.config.clientSecret }}',
       repo: '{{ $.Site.Data.config.repo }}',
       owner: '{{ $.Site.Data.config.owner }}',
       admin: ['{{ $.Site.Data.config.owner }}'],
       id: location.pathname, 
       distractionFreeMode: true // Facebook-like distraction free mode
   })
   </script>
```

Added font-family enforcement under [base.scss](https://github.com/janeilagan/quartz/blob/digital-garden/assets/styles/base.scss) as for some reason the userid is using different font
```css
#gitalk-container {
  font-family: var(--font-header);
}
```

Updated config.yaml with clientID, clientSecret, repo, owner, admin values as defined [here](https://github.com/gitalk/gitalk#method-one)

Also added parameter in config.yaml
```yaml
enableGitalk: true
```


Updates on [single.html](https://github.com/janeilagan/quartz/blob/digital-garden/layouts/_default/single.html) to render gitalk container on line 23.
```html
      {{partial "comments.html" . }}
```

Created comments.html under partials

```html

{{ if (and $.Site.Data.config.enableGitalk (ne .Params.enableGitalk false)) }}

<hr>

<div id="gitalk-container"></div>
    <script>
    (function() {
    if (["localhost", "127.0.0.1"].indexOf(window.location.hostname) != -1) {
      document.getElementById('gitalk-container').innerHTML = 'Gitalk comments not available by default when the website is previewed locally.';
      return;
    }
    gitalk.render('gitalk-container');
  })();
    </script>

{{end}}
```

Every markdown file now can detect metadata of enableGitalk: true or false to load up Gitalk