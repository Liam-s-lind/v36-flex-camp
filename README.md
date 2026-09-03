# Varför Flexbox passar aktivitetskorten

Flexbox passar mina aktivitetskort eftersom de ska ligga bredvid varandra i en riktning. I `style.css` är `.kort-rad` själva "hyllan", där jag har satt `display: flex`. 
De direkta barnen, `<article class="kort">` i `index.html`, blir då flex-items – alltså "böckerna" på hyllan – utan att jag behöver ge dem manuella procentbredder.
 Regeln `flex: 1 1 200px` gör i stället att korten kan växa och krympa med en lämplig grundstorlek på 200 pixlar.

I samma `.kort-rad` skapar `gap: 1rem` ett jämnt mellanrum mellan de olika korten, och `flex-wrap: wrap` låter dem flytta ned till nästa rad när skärmen blir för smal.
 Grid är främst till för tvådimensionella layouter där både rader och kolumner behöver styras samtidigt; det behövdes inte här eftersom korten bara ordnas längs en huvudriktning och får radbrytas automatiskt.