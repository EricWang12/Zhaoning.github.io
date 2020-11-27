## Things to remember:

change social.html:

add 
```html
<span class="username">{{social.github}}</span>

```

 to 
 
```html
  {%- if social.github -%}<li><a rel="me" href="https://github.com/{{ social.github | cgi_escape | escape }}" title="{{ social.github | escape }}"><svg class="svg-icon grey"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg><span class="username">{{social.github}}</span></a></li>{%- endif -%}

```
to update any social

