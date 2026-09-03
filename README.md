# Varför Flexbox passar aktivitetskorten

Flexbox passar mina aktivitetskort eftersom de ska ligga bredvid varandra i en riktning. I `style.css` är `.kort-rad` själva "hyllan", där jag har satt `display: flex`. 
De direkta barnen, `<article class="kort">` i `index.html`, blir då flex-items – alltså "böckerna" på hyllan – utan att jag behöver ge dem manuella procentbredder.
 Regeln `flex: 1 1 200px` gör i stället att korten kan växa och krympa med en lämplig grundstorlek på 200 pixlar.

I samma `.kort-rad` skapar `gap: 1rem` ett jämnt mellanrum mellan de olika korten, och `flex-wrap: wrap` låter dem flytta ned till nästa rad när skärmen blir för smal.
 Grid är främst till för tvådimensionella layouter där både rader och kolumner behöver styras samtidigt; det behövdes inte här eftersom korten bara ordnas längs en huvudriktning och får radbrytas automatiskt.

 ## Varför Flexbox passar mitt innehåll

 Flexbox passar mina aktivitetskort eftersom de ska ligga i en riktning med jämna mellanrum och kunna radbrytas automatiskt på smala skärmar.

## Feedback på en klasskamrats kod
-
```html
<section>
  <div style="display: flex;">
    <div class="card" style="display: flex">Workshop</div>
    <div class="card">Fika</div>
    <div class="card">Brädspel</div>
  </div>
</section>


.card {
  margin: 20px;
}
```
-

FEEDBACK 1: Flytta `style="display: flex;"` från HTML-koden → ge behållaren en klass och skriv `display: flex` i CSS, så blir struktur och design tydligare åtskilda.

FEEDBACK 2: Det första kortet har `display: flex` trots att kortets enda innehåll är text → ta bort regeln eftersom det är behållaren och inte kortet som behöver ordna flera kort med Flexbox.

FEEDBACK 3: `.card { margin: 20px; }` lägger marginal även runt ytterkanterna och kan ge dubbelt avstånd mellan korten → använd `gap: 20px` på flex-behållaren för jämna mellanrum.

FEEDBACK 4: Behållaren saknar `flex-wrap` → lägg till `flex-wrap: wrap` så att korten kan flyttas till en ny rad på smala skärmar.