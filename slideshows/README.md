
### Example file tree for hosting jupyter presentations
```
eaton-lab.github.io/  
|
+-- slideshows/  
    +-- reveal.js/  
    |
    +-- slideshow_1/  
    |   +-- notebook_1.ipynb  
    |   +-- index.slides.html  
    |
    +-- slideshow_2/  
        +-- notebook_2.ipynb  
        +-- index.slides.html  
```  

### Build the HTML presentation
cd into one of the slideshow directories and run *nbconvert* to build the 
presentation as slides. It will build index.slides.html.

```bash
jupyter-nbconvert notebook.ipynb --to slides --output index
```

### Build and serve the notebook slides locally
This will create index.slides.html and serve it on localhost.

```bash
jupyter-nbconvert notebook.ipynb --to slides --output index --post serve
```

### hosting on github
This will write the slides.html file with the path to the local version 
of reveal.js set (shown in the file tree at the top of page). I also 
rename the html file to index.html before pushing to github.

```bash
jupyter-nbconvert notebook.ipynb --to slides --reveal-prefix=../reveal.js --output index
mv index.slides.html index.html
```