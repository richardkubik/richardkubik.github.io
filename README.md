# Zadanie 1 - Webové publikovanie

Vytvorte webovú prezentáciu (webové sídlo) o sebe. Zamerajte sa jednak na vaše profesné záujmy (napr. projekty, ktoré riešite/riešili ste, čo vás v informatike najviac baví, fascinuje = váš developerský profil) a jednak vaše osobné záujmy, hobby.

V rámci developerského profilu vytvorte sekciu Webové publikovanie, kde budete publikovať všetky tri vaše vypracované zadania z predmetu.

Využite pritom technológie Git + GitHub Pages + Jekyll + Markdown. Využite potenciál statického generátora Jekyll a jeho templatovacích možností.

Podrobné požiadavky na vypracovanie a odovzdanie zadania (priemerná úroveň kvality):

* Sídlo musí obsahovať aspoň 5 podstránok, pri využití aspoň 3 rôznych rozložení (layout-ov)

* V rámci šablon musí byť použité:

	* aspoň 5 premenných
	* kolekcie alebo dátové súbory
	* aspoň 5 filtrov alebo tagov
	* aspoň 1 plugin (okrem pagination)


Stránka personálneho webu: [richardkubik.github.io](https://richardkubik.github.io/), testovaná na prehliadači Google chrome verzia 65.


## Požiadavky:

### aspoň 5 podstránok:
* [Homepage](https://richardkubik.github.io/) - úvodná stránka
* [Blog](https://richardkubik.github.io/blog/blog.html) - blog s novinkami
* [Galéria](https://richardkubik.github.io/gallery.html) - galéria s niekoľkými fotkami
* [O mne](hhttps://richardkubik.github.io/about.html) - stručný životopis
* [Projekty](https://richardkubik.github.io/projects.html) - zoznam a informácie o mojich projektoch
* podstránky blogu: napr. https://richardkubik.github.io/sport/2018/03/08/gajdos-spomina.html

### aspoň 3 layouty:
* default - základné rozloženie stránky, obsahuje header, footer, využíva ho takmer každá podstránka
* post - nachádza sa v jednotlivých článkoch blogu
* proj - je na podstránke "Projekty", je pridaný sidebar pre rýchlu navigáciu v zozname projektov

### aspoň 5 premenných:
* tagy
* email
* tel. číslo
* url
* date 
* atribúty v kolekci
### Kolekcie alebo dátové súbory:
Kolekcia využíta pri projektoch, v zložke my_projects.

### aspoň 5 filtrov alebo tagov:
Filtre a tagy využité hlavne pri blogu. 

Zoznam tagov:
* for / endfor
* assign 
* if / endif
* unless 
* contains
* include

Zoznam filtrov:
* date_to_string - využité na podstránke blogu


### aspoň 1 plugin:
Využil som plugin "jekyll-youtube" ktorý z YouTube URL vytovrí snippet aby sa video dalo prehrávař priamo na stránke. Plugin je využitý na podstránke "Galéria", ale GitHub ho nerozozná, preto treba spustiř stránku lokálne.