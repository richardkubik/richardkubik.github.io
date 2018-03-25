---
layout: default
---

<div><h1>Zadanie<h1></div>


<div id="zadanie">
            <p>Predmetom 2. zadania je spracovanie vybraného dokumentu (ideálne bakalárskeho projektu) z pôvodného ľubovoľného (Word, OpenOffice, LaTeX, …) formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument bude mať rozsah minimálne 10 a maximálne 15 strán. Do rozsahu sa nezapočítavajú úvodné strany (obsah, zoznamy obrázkov a tabuliek), použitá literatúra a prílohy.</p>
</div>

<div><h1>Požiadavky<h1></div>

<div>
	<h3>1. štandardné členenie textu na kapitola, podkapitola, podpodkapitola, príloha, obsah</h3>
	</div>


	<p>Na členenie som používal DocBook tagy ako <b>&lt;chapter&gt;</b> pri kapitolách, <b>&lt;section&gt;</b> pri podkapitolách a vnorený  <b>&lt;section&gt;</b> pri podpodkapitolách. Obsah je týmto automaticky generovaný. Nižšie je ukážka obsahu z výsledného PDF.</p>
	<img src="./images/content_preview.png"/>


	<h3>2. zvýraznenie slov, zvýraznenie členenia textu odrážkami alebo číslovaním</h3>

	
	<p>Niektoré slová alebo vety sú v texte tučné, na to som použil tagy <b>&lt;emphasis role="strong"&gt;Slovo&lt;/emphasis&gt;</b> ktoré urobia bold, alebo miesto "strong" som použil "italic" ktoré spôsobia kurzívu. Pre dosiahnutie členenia textu som používal  <b>&lt;itemizedlist&gt;</b>  pri odrážkovaní, a pri číslovaní  <b>&lt;orderedlist&gt;</b> 
	</p>
	
	
	<h3>3. odkazy na iné časti vlastného dokumentu, prípadne odkazy na URL</h3>
	
	<p>Text je plne citovaný, to znamená že každé číslo odkazuje na príslušnú literatúru. Na dosiahnutie tohoto som použil tag <b>&lt;xref linkend="odkaz" /&gt;.</b> Na odkazovanie na inú časť textu som zase použil 
	<b>&lt;link  linkend="odkaz"&gt;(číslo odseku)&lt;/link&gt;</b>. Po obsahu je taktiež zoznam obrázkov a tabuliek, ktoré odkazujú na miesta daných elementov v texte.</p>.

	<h3>4. poznámka pod čiarou</h3>

	<p>Na poznámku pod čiarou som použil tag <b>&lt;footnote&gt;</b></p>
	
	```xml<index type="name"/>```

	<h3>5. zoznam použitej literatúry a zdrojov vrátane ich citácie v texte</h3>

	<p>Na jednotlivé zložky bibliografie som používal tag &lt;bibliomixed&gt;. Ako už je spomenuté v bode 3, bibliografia je zahrnutá na konci dokumentu a všetky odkazy v textových citáciách sú funkčné a odkazujú na danú literatúru.</p>

	<h3>6. vloženie obrázku a tabuliek, odkazy na ne v texte; zoznam obrázkov a tabuliek v úvode alebo závere textu</h3>

	<p>V texte sa náchadza jedna tabuľka (tabuľka pojmov). Na jej vytvorenie som použil <b>&lt;table&gt;</b>. V texte sa ďalej nachádza niekoľko obrázkov ktoré sú vložené pomocou tagu <b>&lt;imagedata fileref="meno súboru" /&gt;</b>. Zoznam obrázkov a tabuliek je hneď po obsahu dokumentu, a bol vytvorený tak, že do thesis.xsl som na riadku 176 zvolil, aby pri tvorbe odsahu tvorilo aj zoznam obrázkov a tabuliek tým, že som doplnil parametre "table" a "figure".</p>

	<h3>7. vytvorenie registra pojmov (indexu) s pojmami hierarchicky usporiadanými do dvoch úrovni, napríklad „cykly, while“, „cykly, for“ (najmenej ako ukážku na 10-15 pojmoch na predvedenie práce s registrom).</h3>

	<p>Pre dosiahnutie registra pojmov som použil tag &lt;indexterm&gt; a na dosiahnutie členenia v ňom &lt;primary&gt; a ku kažému primárnemu som priradil niekoľko skundárnych pojmov pomocou tagu &lt;secondary&gt;.</p>

	<h3>Iné zmeny</h3>

	<p>Odstránenie obrázku na začiatku dokumentu som dosiahol odstránením elementu pre vloženie externého obrázku v súbore thesis-tp-fo.xsl. Riadok číslo 47. Odstránené vkladanie názvu kapitol napr. "Kapitola 1" v dokuemtne, thesis.xsl - zakomentovanie riadku 297-302 by to nevkládalo pri kapitole text "kapitola", a potom pridanie pred vlastný názov kapitoly čislo pomocou <b>&lt;xsl:apply-templates select="$node" mode="label.markup"/&gt;</b> a bodku pomocou <b>&lt;xsl:text&gt;. &lt;/xsl:text&gt;</b>. XML som overil v nástroji XMLMind a je plne validný.</p>

  <a href="/webove_pub.html"><img src="/images/back.png