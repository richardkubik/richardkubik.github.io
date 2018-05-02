# Zadanie 3 - Dokumentácia

Predmetom tretieho zadanie bolo navrhnúť vlastný XML súbor, ktorý bude obsahovať prezentáciu, k nemu na validáciu vytvoriť buď DTD, XML Schemu alebo Relax NG. Následny vytvoriť XSLT šablńy na preklad z XML do PDF a XHTML.

## Opis type dokumentu

Na opis typu dokumentu je použitá XML Schema. XML je podľa nej validný.

## Opis elementov XML súboru

Ako koreňový element slúž element:
```
<prezentacia>
```

Jej pod elementy sú:
```
<slajd>
```
Element slajd môže mať atribút "bgcolor", ktorý určuje farbu pozadia

V samotnom slajde môžu byť elementy:
### Názov 
označuje názov celej prezentácie
```
<nazov>
```

### Meno
je to meno autora
```
<meno>
```

### Nadpis
označuje nadpis, ktorý má byť na slajde
```
<nadpis>
```

### Text
označuje jednú odrážku slajdu, môže mať atribút "color", ktorý určuje farbu daného textu
```
<text>
```

c Tabuľka 
skladá sa z hlavičky a následne riadkov
```
<tabulka>
	<hlavicka>
		<stlpec></stlpec>
		<stlpec></stlpec>
	</hlavicka>
	<riadok>
		<stlpec></stlpec>
		<stlpec></stlpec>
	</riadok>
	<riadok>
		<stlpec></stlpec>
		<stlpec></stlpec>
	</riadok>
</tabulka>
```

### Obrázok
vkladaný pomocou atribútu src:
```
<obrázok src="zlozka"/>
```

### Poďakovanie:
označuje ďakovný text za pozornosť na konci prezentácie
```
<podakovanie>
```