## add_header X-Frame-Options

访问：http://localhost:9999/X-Frame-Options-test.html

> 这是保护 X-Frame-Options.html 不被随便嵌入到其它网站

- X-Frame-Options: SAMEORIGIN

如果 X-Frame-Options-test.html 中的 iframe 页面 X-Frame-Options.html 是同域，则可正常显示；否则不能显示

- X-Frame-Options: DENY

X-Frame-Options.html 不能被嵌入到其它网站，同域都不行

## add_header Strict-Transport-Security

这个请求头只有在 HTTPS 请求时才生效，目的就是为了该 HTTPS 请求之后的所有请求都必须使用 HTTPS 请求。所以如果第一个请求是 HTTP 的则无效

> weda 需要访问 wa 服务，，而本地 wa 服务是 http 的，所以不能开启这个响应头

## add_header Content-Security-Policy

限制内容的来源。比如

```
add_header Content-Security-Policy "script-src 'self' cdn.jsdelivr.net";
```

限制脚本只能来源于本站和 cdn.jsdelivr.net

## add_header X-XSS-Protection

设置了 CSP，这个就不用设置了。对于不支持 CSP 的浏览器，则可以用这个来设置

## add_header X-Download-Options

仅仅作用于 IE8

## add_header X-Content-Type-Options

确保 style 类型资源的 MIME 类型为 text/css

确保 script 类型资源的 MIME 类型为 javascript





