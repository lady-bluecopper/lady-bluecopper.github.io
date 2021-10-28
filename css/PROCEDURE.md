# Website Setup
## I'll tell you how I got here

### 1. We need a skeleton

0. Have a git repo , have .gitignore https://github.com/github/gitignore (macOS at least, any oher editor you use)

1. GO to  http://www.initializr.com/

2. Configure it. We want it responsive; with Mobile First template (no Bootstrap, that's a lot of mess); yes for jQuery minified,  
you won't need to see the source; yes fo IE classes; no for Old Browser warning, let the poor users alone they are already suffering; the .htaccess is useful, we will need to edit it; 
let's leave out Google tracking for now; we like Favicon, we like apple icons, we may need plugins, we definetely love robots, but we also like humas (I hope at least those who help us); 404 pages we will have our one leave out their, Adobe cross stuff, may be useful, but not for now.

3. Download and unpack, move to your folder (do backup if you have anything there), here is what we have

        .
        ├── .gitignore
        ├── .htaccess
        │  
        ├── favicon.ico
        ├── robots.txt        
        ├── humans.txt
        ├── index.html        
        ├── tile-wide.png
        ├── tile.png        
        │          
        ├── apple-touch-icon.png
        ├── browserconfig.xml
        ├── css
        │   ├── main.css
        │   ├── normalize.css
        │   └── normalize.min.css
        ├── js
        │   ├── main.js
        │   ├── plugins.js
        │   └── vendor
        │       ├── jquery-1.11.2.min.js
        │       └── modernizr-2.8.3-respond-1.4.2.min.js
        └── img
    

4. Edit the file humans.txt http://humanstxt.org/

### 2. Chose a tool, a helper, a framework

1. When things are simple I use, https://purecss.io/
2. Download the latest version: `curl -LO https://github.com/yahoo/pure-release/archive/v1.0.0.zip` 
3. Did you check that was the latest?
4. Move only the complete file `mkdir -p css/vendor; unzip v1.0.0.zip -d /tmp/; mv -v /tmp/pure-release-1.0.0/pure-min.css  css/vendor`
5. Take the responsive grids `cat /tmp/pure-release-1.0.0/grids-responsive-min.css >> css/vendor/pure-min.css `
5. Cleanup  `rm css/normalize.css css/normalize.min.css`, the good people provided us with normalize, but we have our framework.
6. Update Humans.txt, would you?


### 3. Set it up
0. Open index.html
1. Delete all HTML in the `<body></body>`, but leave th `<script>` tags
2. Replace `<link rel="stylesheet" href="css/normalize.min.css">` with `<link rel="stylesheet" href="css/pure-min.css">`
3. You are ready to rock

### 4. Customization
0. There are a set of png icons in the root. You can change them, but not their dimensions or their name. (For the .ico https://www.favicon-generator.org/)
1. Javascript cod goes into `js/main.js`
2. CSS code in `css/main.css`. Remove all that comes before
 
        /* =============================================
            Author's custom styles
           ============================================= */


   Remove also the content under
   
         /* ====================
         INTERMEDIATE: Menu
         ==================== */


         /* ========================
          INTERMEDIATE: IE Fixes
          ======================== */
          
          /* ====================
              WIDE: CSS3 Effects
              ==================== */
   and all the other sections, down to
   
        /* ================================================
           Helper classes
           ================================================ */
  excluded.
  Now, the CSS file is ready for you content
  
  ### 5. About  Content
  
  0. Use semantic markup:  
      - https://html.com/semantic-markup/
      - https://websitesetup.org/wp-content/uploads/2014/02/HTML-CHEAT-SHEET-768x8555.png
  1. Consider using schema.org markup as metadata for you HTML
      - http://schema.org/docs/gs.html
      - http://schema.org/WebPage
      - http://schema.org/Person
      - https://webmasters.stackexchange.com/questions/87940/new-required-mainentityofpage-for-article-structured-data/87982#87982
      - https://searchengineland.com/schema-markup-structured-data-seo-opportunities-site-type-231077
      - But I would strongly advise against JSON-LD, and would use standard HTML properties


### Test it?
0. python 2: `python -m SimpleHTTPServer` from the root directory, open localhost:8000 (you'll find the similar command for python3)
1. Re:view for chrome https://chrome.google.com/webstore/detail/emmet-review/epejoicbhllgiimigokgjdoijnpaphdp


      
  

  










