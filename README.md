# Zadanie 1 - Webové publikovanie

Vytvorte webovú prezentáciu (webové sídlo) o sebe. Zamerajte sa jednak na vaše profesné záujmy (napr. projekty, ktoré riešite/riešili ste, čo vás v informatike najviac baví, fascinuje = váš developerský profil) a jednak vaše osobné záujmy, hobby.

Podrobné požiadavky na vypracovanie a odovzdanie zadania (priemerná úroveň kvality):

* Sídlo musí obsahovať aspoň 5 podstránok, pri využití aspoň 3 rôznych rozložení (layout-ov)

* V rámci šablon musí byť použité:

	* aspoň 5 premenných
	* kolekcie alebo dátové súbory
	* aspoň 5 filtrov alebo tagov
	* aspoň 1 plugin (okrem pagination)


Stránka personálneho webu: [richardkubik.github.io](https://richardkubik.github.io/)

### Testované na:
* Google Chrome

## Použité technológie:

* Git
* GitHub Pages
* Jekyll
* Markdown


## Splnené požiadavky:

### Podstránky:
1. [Homepage](https://richardkubik.github.io/) - úvodná stránka
2. [Blog](https://richardkubik.github.io/blog/blog.html) - blog s novinkami
3. [Galéria](https://richardkubik.github.io/gallery.html) - galéria s niekoľkými fotkami
4. [O mne](https://richardkubik.github.io/about.html) - stručný životopis
5. [Projekty](https://richardkubik.github.io/projects.html) - zoznam a informácie o mojich projektoch
6. podstránky blogu: napr. https://richardkubik.github.io/sport/2018/03/08/gajdos-spomina.html

### Layouty:
1. default - základné rozloženie stránky, obsahuje header, footer, využíva ho takmer každá podstránka
2. post - nachádza sa v jednotlivých článkoch blogu
3. proj - je na podstránke "Projekty", je pridaný sidebar pre rýchlu navigáciu v zozname projektov

### Premenné:
1. tagy
2. email
3. tel. číslo
4. url
5. dátum 
6. atribúty v kolekci

### Kolekcia:
- využíta pri projektoch, v zložke my_projects.

### Tagy a filtre:

Filtre a tagy využité hlavne pri blogu. 

#### Tagy
1. for / endfor
2. assign 
3. if / endif
4. unless 
5. contains
6. include
7. comment

#### Filtre
1. date_to_string - využité na podstránke blogu


### Plugin:
Využil som plugin "jekyll-youtube" ktorý z YouTube URL vytvorí snippet aby sa video dalo prehrávať priamo na stránke. Plugin je využitý na podstránke "Galéria", ale GitHub ho nerozozná, preto treba spustiť stránku lokálne.