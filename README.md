# arial-bold-madness

https://bugs.chromium.org/p/chromium/issues/detail?id=627143#c37

> Another data point: this affects the CSS provided by fonts.googleapis.com causing locally installed fonts to be ignored.
> 
> Example:
> Chrome: 63.0.3239.132 
> OS: Windows 10
> 
> Linking "http://fonts.googleapis.com/css?family=Special+Elite"
> 
> Returns this CSS:
> 
>     /* latin */
>     @font-face {
>       font-family: 'Special Elite';
>       font-style: normal;
>       font-weight: 400;
>       src: local('Special Elite Regular'), local('SpecialElite-Regular'), url(http://fonts.gstatic.com/s/specialelite/v8/9-wW4zu3WNoD5Fjka35JmzxObtw73-qQgbr7Be51v5c.woff2) format('woff2');
>       unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2212, U+2215;
>     }
>
> The src correctly references the font face name. Chrome does not find the locally installed font and falls back to using the web font. Firefox does find the locally installed font.
>
> If you modify the CSS to reference local('Special Elite') (i.e. the font family name), then the behaviour is reversed: Chrome finds the local font and Firefox does not.
