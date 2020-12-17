
HTML-indholdet  udstilles som GitHub Pages[1] her: https://digst.github.io/bikeshed-template/docs/

Her ligger følgende filer:
- README.md - Denne fil
- index.md - Mastertekst i Markdown-format 
- index.html - Mastertekst konverteret til html

# Sådan anvendes Bikeshed som skabelon til udstilling af specifikationer

## 1 Aktivér GitHub Pages
Udstilling via GitHub Pages kan aktiveres via repositoriets 'Settings' (scroll ned til GitHub Pages)

## 2 Konvertér eventuelt Word (docs) indhold til MD
Word (docx) filer kan konverteres til Markdown via fx: https://euangoddard.github.io/clipboard2markdown/

## 3 Konvertér MD til HTML 
Konvertering af Markdown-indhold til HTML kan fx ske via Bikeshed's webformular: https://api.csswg.org/bikeshed/
  
- Kopier index.md-teksten fra GitHub ind i Bikeshed's webformular: https://api.csswg.org/bikeshed/
- Vælg Output = Generated HTML og vælg Force HTML. og klik 'Proces'
- Hvis alt ser ok ud (selvom billederne vil mangle), så ’Vis kilde’ og kopier HTML-outputtet
- Åbn index.html-filen på GitHub og indsæt HTML-outputtet og gem
- Vent 3-5 minutter på at GitHub pages genererer visningen: 

## 4 Tilføj tabindex i HTML-filen (WCAG) 
Indsæt følgende script nederst i body i index.html filen, for at tilføje tabindex i indholdsfortegnelse:

<script>
    /*Set attribute tabindex on all elements in TOC*/
    var toc =  document.querySelectorAll("#toc .content");
    for (var i = 0; i < toc.length; i++) {
      if (!toc[i].hasAttribute("tabindex")){
        var att = document.createAttribute("tabindex");
        att.value = "0";
        toc[i].setAttributeNode(att);
      }
    }
    /*Set lang attribute value to "da" in html tag*/
    document.getElementsByTagName("html")[0].setAttribute("lang", "da");
</script>
