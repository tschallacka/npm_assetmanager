An asset loader for use in javascript projects.

It loads images, Javascript and CSS when they haven't been loaded in the DOM yet, and prevents double inclusion of the same files.
Do note that filenames are case sensitive and timestamps do matter.

installation:

     npm install @tschallacka/assetmanager

# AssetManager.load ( toload, callback )

**toload**  
This method takes an object as argument with 3 properties, css, js and img as String arrays.
     
     {
     js : ['file.js'],
     css : ['file.css'],
     img : ['file.jpg']
     }

**callback**  
A function to call when the files have been loaded.

# Example:

     var AssetManager = require('@tschallacka/assetmanager');
     window.assetManager = new AssetManager();
  
     .....
         </footer>
         <script type="text/javascript">
             assetManager.load({ 
                css:["https://www.domain.com/css/map-styles.css?1501496092",
                     "https://fonts.googleapis.com/css?family=Roboto+Condensed:300,300i,400,400i,700,700i|Raleway:300,300i,400,400i,500,500i,600,600i,700,700i,800,800i,900,900i|Open+Sans:300,300i,400,400i,600,600i,700,700i,800,800i|Quicksand:300,400,500,700|Montserrat:100,100i,200,200i,300,300i,400,400i,500,500i,600,600i,700,700i,800,800i,900,900i&amp;subset=latin-ext"], 
                js:["https://www.domain.com/js/img.js?1546617773",
                    'https://www.domain.com/js/social_interaction.js?time=1546617773'], 
                img:[] 
             }, function(){
                console.log('triggering render');
                $(document).trigger('render');
             });
          </script>
       </body>
    </html>
