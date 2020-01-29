### Kodlarınızı Renklendirin

Web sayfalarınızda kod örnekleri paylaşırken, kodların daha anlaşılır olabilmesi için kodlarınızı renklendirmek isteyebilirsiniz. Bununla ilgili çok fazla javascript eklentisi bulunmakta, bizde sizlere [highlightjs.org](https://highlightjs.org)'da yer alan örneği göstermek istedik.

Yapmanız gereken ilk olarak script dosyasını sayfanıza dahil etmek ve çalıştırmak;
```html
<script src="https://cdn.jsdelivr.net/gh/highlightjs/cdn-release@9.18.0/build/highlight.min.js"></script>
<script>
	hljs.initHighlighting();
</script>
```

Daha sonra mevcut css renklerini kendinize göre uyarlayarak kullanabilirsiniz;
```css
pre {
    background: #222;
    padding: 15px;
}

.hljs {
  display: block;
  overflow-x: auto;
  padding: 0.5em;
  color: #abb2bf;
  background: rgba(255, 255, 255, .07);
}

.hljs-comment,
.hljs-quote {
  color: #5c6370;
  font-style: italic;
}

.hljs-doctag,
.hljs-keyword,
.hljs-formula {
  color: #c678dd;
}

.hljs-section,
.hljs-name,
.hljs-selector-tag,
.hljs-deletion,
.hljs-subst {
  color: #e06c75;
}

.hljs-literal {
  color: #56b6c2;
}

.hljs-string,
.hljs-regexp,
.hljs-addition,
.hljs-attribute,
.hljs-meta-string {
  color: #98c379;
}

.hljs-built_in,
.hljs-class .hljs-title {
  color: #e6c07b;
}

.hljs-attr,
.hljs-variable,
.hljs-template-variable,
.hljs-type,
.hljs-selector-class,
.hljs-selector-attr,
.hljs-selector-pseudo,
.hljs-number {
  color: #d19a66;
}

.hljs-symbol,
.hljs-bullet,
.hljs-link,
.hljs-meta,
.hljs-selector-id,
.hljs-title {
  color: #61aeee;
}

.hljs-emphasis {
  font-style: italic;
}

.hljs-strong {
  font-weight: bold;
}

.hljs-link {
  text-decoration: underline;
}
```

Ve sonuç olarak şu şekilde kullanabilirsiniz;
```html
<pre><code class="language-html"> <!-- html kodlarınız --></code></pre>
```

`language-x` = burada x yerine dilin adını yazmanız yeterli. Örneğin; css, javascript, php, go, python vb.
