url: /zadanie2

# Zadanie

Predmetom 2. zadania je spracovanie vybraného dokumentu (ideálne bakalárskeho projektu) z pôvodného ľubovoľného (Word, OpenOffice, LaTeX, …) formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument bude mať rozsah minimálne 10 a maximálne 15 strán. Do rozsahu sa nezapočítavajú úvodné strany (obsah, zoznamy obrázkov a tabuliek), použitá literatúra a prílohy.


## Požiadavky

### 1.štandardné členenie textu na kapitola, podkapitola, podpodkapitola, príloha, obsah
	

Na členenie som používal DocBook tagy ako **&lt;chapter&gt;** pri kapitolách, <b>&lt;section&gt;</b> pri podkapitolách a vnorený  <b>&lt;section&gt;</b> pri podpodkapitolách. Obsah je týmto automaticky generovaný. Takto to je v DocBooku:
```
	<chapter>
	(kapitola)
		<section>
		(podkapitola)
			<section>
			(podpodkapitola)
			</section
		</section>
	</chapter>
```


### 2. zvýraznenie slov, zvýraznenie členenia textu odrážkami alebo číslovaním

	
Niektoré slová alebo vety sú v texte tučné, na to som použil tagy ```<emphasis role="strong">Slovo</emphasis>``` ktoré urobia bold, alebo miesto "strong" som použil ```<emphasis role="italic">Slovo</emphasis>```, ktoré spôsobia kurzívu. Pre dosiahnutie členenia textu som používal následujúce tagy:
* číslovanie: **orderedlist**
* odrážkovanie: **itemizedlist**


```
	<itemizedlist> alebo pre číslovanie: <orderedlist>
		<listitem>
			<para>prvá vec</para>
		</listitem>
		<listitem>
			<para>druhá vec</para>
		</listitem>
	</itemizedlist> alebo pre číslovanie: </orderedlist>
```
	
	
### 3. odkazy na iné časti vlastného dokumentu, prípadne odkazy na URL
	
Text je plne citovaný, to znamená že každé číslo odkazuje na príslušnú literatúru. Na dosiahnutie tohoto som použil tag```<xref linkend="odkaz" />```. Na odkazovanie na inú časť textu alebo obrázku som zase použil 
```<link linkend="odkaz">(id elementu)</link>```>. Po obsahu je taktiež zoznam obrázkov a tabuliek, ktoré odkazujú na miesta daných elementov v texte.

### 4. poznámka pod čiarou

Na poznámku pod čiarou som použil tag ```<footnote>```
```
<footnote>
	<para>
	Text pod čiarou
	</para>
</footnote>
```
	
	

### 5. zoznam použitej literatúry a zdrojov vrátane ich citácie v texte

Jednotlive zložky bibliografie sú napísané ako:
```
<bibliomixed id="templates">Eriks Sneiders: 
	<title>
	Automated Question Answering 
	Using Question Templates That Cover the Conceptual Model of the Database.
	</title> 
	2002
</bibliomixed>
```

Ako už je spomenuté v bode 3, bibliografia je zahrnutá na konci dokumentu a všetky odkazy v textových citáciách sú funkčné a odkazujú na danú literatúru pomocou ```<xref linkend="odkaz na danú literatúru" />```

### 6. vloženie obrázku a tabuliek, odkazy na ne v texte; zoznam obrázkov a tabuliek v úvode alebo závere textu

V texte sa náchadza jedna tabuľka (tabuľka pojmov). Na jej vytvorenie som použil ```<table>```:
```
<table id="tabulka_pojmov" frame='all'>
	<title>Slovník pojmov</title>
	<tgroup cols='2' align='left' colsep='1' rowsep='1'>
		<thead>
			<row>
  				<entry align="center">Skratka</entry>
  				<entry align="center">Slovný druh</entry>
			</row>
		</thead>
		<tbody>
			<row>
  				<entry>NN</entry>
  				<entry>podstatné meno</entry>
			</row>
			<row>
  				<entry>NNP</entry>
  				<entry>vlastné podstatné meno</entry>
			</row>
			<row>
  				<entry>CD</entry>
  				<entry>číslovka</entry>
			</row>
			<row>
  				<entry>NP</entry>
  				<entry>podstatné meno</entry>
			</row>
			<row>
  				<entry>VZ/V</entry>
  				<entry>sloveso</entry>
			</row>
			<row>
  				<entry>IN</entry>
  				<entry>predložka</entry>
			</row>
		</tbody>
	</tgroup>
</table> 
```
 V texte sa ďalej nachádza niekoľko obrázkov ktoré sú vložené ako ```<figure>```:
 ```	
 <figure id="sentence_parse">
  <title>Veta rozdelená do stromu podľa slovných druhov</title>
  <mediaobject>
    <imageobject>
      <imagedata fileref="parsed_sentence.png" />
    </imageobject>
  </mediaobject>
</figure>
```
Zoznam obrázkov a tabuliek je hneď po obsahu dokumentu, a bol vytvorený tak, že do thesis.xsl som na riadku 176 doplnil parametre tak, aby pri tvorbe odsahu tvorilo aj zoznam obrázkov a tabuliek:
```
<xsl:param name="generate.toc">
book      title,toc,figure,table 
</xsl:param>
```


### 7. vytvorenie registra pojmov (indexu) s pojmami hierarchicky usporiadanými do dvoch úrovni, napríklad „cykly, while“, „cykly, for“ (najmenej ako ukážku na 10-15 pojmoch na predvedenie práce s registrom).

Pre dosiahnutie registra pojmov som použil tag ```<indexterm>```, do dokumentu som ho vložil na koniec pomocou ```</index>```, a v texte som doňho zapisoval pojmy takto:
```	
<indexterm>
	<primary>Automatizovaná tvorba otázok</primary>
	<secondary>veta</secondary>
</indexterm>
```


### 8. Iné zmeny

Odstránenie obrázku na začiatku dokumentu som dosiahol odstránením elementu pre vloženie externého obrázku v súbore thesis-tp-fo.xsl. Riadok číslo 47:
```
<!--  <fo:external-graphic src="url(kizi.pdf)" width="2cm" content-width="scale-to-fit"/> -->
```
 
 Odstránené vkladania názvu kapitol napr. "Kapitola 1" v dokumente, thesis.xsl - zakomentovanie riadku 297-302 aby to nevkládalo pri kapitole text "kapitola", ale len napr. 1. Úvod:
```
<fo:block xsl:use-attribute-sets="chap.title.properties">
    <xsl:apply-templates select="$node" mode="label.markup"/>
    <xsl:text>. </xsl:text>
    <xsl:apply-templates select="$node" mode="title.markup"/>
</fo:block>
```
