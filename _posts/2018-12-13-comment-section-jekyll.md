---
layout: post
title: "Menambah Kolom Komentar di Jekyll"
comments: true
author: "Imam Nur"
tags: [codding]
---

Setelah beberapa hari dibuat pusing oleh bagaimana caranya menambah kolom komentar pada github page, akhirnya saya menemukan cara yang cukup simple untuk mengatasi masalah tersebut. Dengan cara ini kalian tidak perlu lagi mencari page url dan page identifier seperti kebanyakan metode yang ada di google. Oke langsung saja kita ke tutorialnya.

Pertama-tama buat akun [Disqus](https://disqus.com/profile/signup/) terlebih dahulu. Apabila kalian sudah mempunyai akun Disqus cukup lewati langkah ini.

Selanjutnya buka file `_config.yml` dan tambahkan kode berikut
```html
{% raw %}#Disqus
disqus_shortname: shortname{% endraw %}
```

Ganti shortname dengan [Disqus Shortname](https://help.disqus.com/installation/whats-a-shortname) milik kamu.

Sekarang buka folder `_include` dan buat file baru dengan nama `comments.html` kemudian tambahkan kode berikut di dalamnya.
```html
{% raw %}<div class="container">
<div class="row">
<div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1" id="disqus_thread">

</div>
</div>
</div>
<script type="text/javascript">
    /* * * CONFIGURATION VARIABLES * * */
    var disqus_shortname = '{{ site.disqus_shortname }}';
    
    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>{% endraw %}
```

Terakhir buka `post.html` yang terdapat di folder `_layouts` lalu tambahkan kode berikut.
```html
{% raw %}{% include comments.html %}{% endraw %}
```

Done!.
