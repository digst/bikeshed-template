# bikeshed-template

Bikeshed Template - Læs mere her: https://tabatkins.github.io/bikeshed/


## Anvendelse af Bikeshed som skabelon til udstilling af specifikationer

### 1 Opret mappe til bikeshed-udstilling
- Opret /docs mappe i roden af repositoriet
- Opret eventuelt undermappen /docs/img hvis der skal indgå illustrationer

### 2 Aktivér GitHub Pages
Udstilling via GitHub Pages kan aktiveres via repositoriets 'Settings'
- Gå til repositoriets hovedside
- Vælg Settings (det lille tandjhul)
- Scroll ned til indstillingerne for GitHub Pages
- Aktiver og vælg at opbygge html-visningen fra /docs-mappen fra 'main branch'

### 3 Konvertér eventuelt Word (docs) indhold til MD
Word (docx) filer kan konverteres til Markdown via fx: https://euangoddard.github.io/clipboard2markdown/

### 4 Konvertér MD til HTML 
Konvertering af Markdown-indhold til HTML kan fx ske via Bikeshed's webformular: https://api.csswg.org/bikeshed/
  
- Kopier index.md-teksten fra GitHub ind i Bikeshed's webformular: https://api.csswg.org/bikeshed/
- Vælg Output = Generated HTML og vælg Force HTML. og klik 'Proces'
- Hvis alt ser ok ud (selvom billederne vil mangle), så ’Vis kilde’ og kopier HTML-outputtet
- Åbn index.html-filen på GitHub og indsæt HTML-outputtet og gem
- Vent 3-5 minutter på at GitHub pages genererer visningen: 

### 5 Tilføj tabindex i HTML-filen (WCAG) 
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

