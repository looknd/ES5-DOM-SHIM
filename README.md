# ES5 and DOM4 shim for all browsers with IE6 and IE7 support
based on:

- https://github.com/kriskowal/es5-shim
- https://github.com/paulmillr/es6-shim
- https://github.com/Raynos/DOM-shim

__Next__: [work in progress](https://github.com/termi1uc1/ES5-DOM-SHIM/tree/dev)

## Adding to html:
`in a HEAD section`
    
	<script src="a.js"></script>
    <!--[if lt IE 8]>
    <script src="a.ielt8.js"></script>
    <![endif]-->

## Same-domain limitation

IE requires that the .htc behavior file must be in the same domain as the HTML page which uses it. If you try to load the behavior from a different domain, you will get an "Access Denied" error.
Note that the domain must be exactly the same; that means that http://www.foo.com is a different domain than http://foo.com.
http://css3pie.com/documentation/known-issues/#x-domain

### Solve Same-domain limitation
Russian instruction in extra/SameDomainLimitation.SOLVE_RUS.odt

### Temporary testing
http://jsperf.com/es5-dom-shim-test

## Goal
Main lib (a.js): 7.8 Kib of total minified and gzipped size
IE < 8 support: 2 Kib (a.ielt8.js) + 600 b (a.ielt8.htc) + 150 b (a.ie6.ielt8) of total minified and gzipped size

## Known issues:
1. Same-domain limitation (can be solve only on server)
2. Incompatibility with http://code.google.com/p/ie7-js/ [working on it]

## TODO
0. fix getAttribute/setAttribute for IE6,7 (it should differentiate attributes and properties with same names)
1. hasAttribute
2. element.dataset
**
9. http://dvcs.w3.org/hg/url/raw-file/tip/Overview.html