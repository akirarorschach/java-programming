---
path: "/osa-1/4-muuttujat"
title: "Laskentaa luvuilla"
---


<% partial 'partials/learning_objectives', locals: { name: 'Oppimistavoitteet' } do %>

  <ul>
    <li>
      Osaat tehdä laskutoimintoja muuttujien avulla.
    </li>
    <li>
      Osaat muodostaa tulostuslauseita, jossa on mukana sekä laskuoperaatioita (lausekkeita) että merkkijonoja.
    </li>

  </ul>

<% end %>




<p>
  voiko int-arvoon lisätä doublen tai toisinpäin?
</p>


<p>
  Laskuoperaatiot ovat tuttuja ja suoraviivaisia: yhteenlasku <code>+</code>, erotus <code>-</code>, kertolasku <code>*</code> ja jakolasku <code>/</code>. Laskentajärjestys on myös tuttu: laskenta tehdään vasemmalta oikealle sulut huomioon ottaen. Kuitenkin <code>*</code> ja <code>/</code> lasketaan ennen <code>+</code> ja <code>-</code> operaatioita, samoin kuin perus- tai kansakoulumatematiikassa on tullut tutuksi.
</p>

<% partial 'partials/code_highlight' do %>
int eka = 2;
System.out.println(eka); // tulostaa 2
int toka = 4;
System.out.println(toka); // tulostaa 4

int summa = eka + toka; // muuttujaan summa asetetaan muuttujien eka ja toka arvojen summa
System.out.println(summa); // tulostaa 6
<% end %>


<% partial 'partials/material_sub_heading' do %>
  Laskujärjestys ja sulut
<% end %>

<p>
  Laskujärjestykseen voi vaikuttaa sulkujen avulla. Sulkujen sisällä olevat laskuoperaatiot suoritetaan ennen niiden ulkopuolella olevia laskuoperaatioita.
</p>

<% partial 'partials/code_highlight' do %>
int laskuSuluilla = (1 + 1) + 3 * (2 + 5);
System.out.println(laskuSuluilla); // tulostaa 23

int laskuSuluitta = 1 + 1 + 3 * 2 + 5;
System.out.println(laskuSuluitta); // tulostaa 13
<% end %>


<p>
  Yllä olevan esimerkin voi jakaa myös osiin.
</p>

<% partial 'partials/code_highlight' do %>
int laskuSuluilla = (1 + 1);
System.out.println(laskuSuluilla); // tulostaa 2
laskuSuluilla = laskuSuluilla + 3 * (2 + 5);
System.out.println(laskuSuluilla); // tulostaa 23

int laskuSuluitta = 1 + 1;
laskuSuluitta = laskuSuluitta + 3 * 2;
laskuSuluitta = laskuSuluitta + 5;
System.out.println(laskuSuluitta); // tulostaa 13
<% end %>



<% partial 'partials/exercise', locals: { name: 'Sekunnit vuorokaudessa', model_solution: '50222' } do %>

  <p>
    Toteuta tehtäväpohjaan ohjelma, joka kysyy käyttäjältä vuorokausien lukumäärää. Tämän jälkeen ohjelma tulostaa sekuntien määrän annetuissa vuorokausissa.
  </p>

  <p>
    Esimerkkitulostuksia:
  </p>

  <% partial 'partials/sample_output' do %>
    Kuinka monen vuorokauden sekunnit tulostetaan?
    <font color="red">3</font>
    259200
  <% end %>

  <% partial 'partials/sample_output' do %>
    Kuinka monen vuorokauden sekunnit tulostetaan?
    <font color="red">7</font>
    604800
  <% end %>

<% end %>

<%= partial 'partials/quiz', locals: { id: '5a57bcce574f0b000439a32b' } %>

<% partial 'partials/hint', locals: { name: 'Lauseke ja lause' } do %>

  <p>
    Lauseke (expression) on arvojen yhdistelmä, joka muuntuu arvoksi laskuoperaation tai evaluaation yhteydessä. Alla oleva lause sisältää lausekkeen <code>1 + 1 + 3 * 2 + 5</code>, joka evaluoidaan ennen arvon asetusta muuttujaan.
  </p>

  <% partial 'partials/code_highlight' do %>
int laskuSuluitta = 1 + 1 + 3 * 2 + 5;
  <% end %>

  <p>
    Lausekkeen evaluaatio tapahtuu aina ennen muuttujan arvon asetusta, eli yllä lasku "1 + 1 + 3 * 2 + 5" suoritetaan ennen tuloksen asetusta muuttujaan.
  </p>

<% end %>

<p>
  Lausekkeen evaluointi tapahtuu ohjelmakoodissa siinä kohtaa, missä lauseke on. Evaluointi onnistuu siis esimerkiksi myös tulostuslauseen yhteydessä, jos lauseketta käytetään tulostuslauseen parametrin arvon laskemisessa.
</p>

<% partial 'partials/code_highlight' do %>
int eka = 2;
int toka = 4;

System.out.println(eka + toka); // tulostaa 6
System.out.println(2 + toka - eka - toka); // tulostaa 0
<% end %>


<p>
  Lauseke ei muuta muuttujassa olevaa arvoa, ellei lausekkeen lopputulosta aseteta muuttujan arvoksi tai anneta parametrina esimerkiksi tulostukselle.
</p>

<% partial 'partials/code_highlight' do %>
int eka = 2;
int toka = 4;

// alla oleva lauseke ei edes toimi, sillä lauseketta
// ei aseteta minkään muuttujan arvoksi tai anneta parametrina
// tulostuslauseelle
eka + toka;
<% end %>


<%= partial 'partials/quiz', locals: { id: '5878a0b579db890004df0d1d' } %>


<% partial 'partials/material_sub_heading' do %>
  Laskentaa ja tulostamista
<% end %>

<p>
  Muuttujan arvon voi tulostaa komennolla <code>System.out.println</code>. Tulostettavaan hipsuilla merkittyyn merkkijonoon, esim. "Pituus ", voidaan lisätä muuta tulostettavaa operaation <code>+</code> avulla.
</p>

<% partial 'partials/code_highlight' do %>
int pituus = 42;
System.out.println("Pituus " + pituus);
<% end %>

<% partial 'partials/sample_output' do %>
Pituus 42
<% end %>

<% partial 'partials/code_highlight' do %>
System.out.println("tuossa on kokonaisluku --&gt; " + 2);
System.out.println(2 + " &lt;-- tuossa on kokonaisluku");
<% end %>

<% partial 'partials/sample_output' do %>
tuossa on kokonaisluku --&gt; 2
2 &lt;-- tuossa on kokonaisluku
<% end %>

<p>
  Jos toinen operaation <code>+</code> kohteista on merkkijono, muutetaan myös toinen operaation kohteista merkkijonoksi ohjelman suorituksen yhteydessä. Alla olevassa esimerkissä kokonaisluku <code>2</code> on muutettu merkkijonoksi "2", ja siihen on yhdistetty merkkijono.
</p>

<p>
  Aiemmin esitellyt laskusäännöt pätevät täälläkin:
</p>

<% partial 'partials/code_highlight' do %>
System.out.println("Neljä: " + (2 + 2));
System.out.println("Mutta! kaksikymmentäkaksi: " + 2 + 2);
<% end %>

<% partial 'partials/sample_output' do %>
Neljä: 4
Mutta! kaksikymmentäkaksi: 22
<% end %>

<div class="code-states-visualizer-widget" data-input='{"code":"public class Esimerkki {\n    public static void main(String[] args) {\n        System.out.println(\"Neljä: \" + (2 + 2));\n        System.out.println(\"Mutta! kaksikymmentäkaksi: \" + 2 + 2);\n    }\n}","stdin":"","trace":[{"stdout":"","event":"call","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"1","frame_id":1}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"2","frame_id":2}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Neljä: 4\n","event":"step_line","line":4,"stack_to_render":[{"func_name":"main:4","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"5","frame_id":5}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Neljä: 4\nMutta! kaksikymmentäkaksi: 22\n","event":"step_line","line":5,"stack_to_render":[{"func_name":"main:5","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"8","frame_id":8}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Neljä: 4\nMutta! kaksikymmentäkaksi: 22\n","event":"return","line":5,"stack_to_render":[{"func_name":"main:5","encoded_locals":{"__return__":["VOID"]},"ordered_varnames":["__return__"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"9","frame_id":9}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}}],"userlog":"Debugger VM maxMemory: 455M\n"}'></div>


<% partial 'partials/exercise', locals: { name: 'Kahden luvun summa', model_solution: '50223' } do %>

  <p>
    Kirjoita ohjelma, joka kysyy käyttäjältä kahta lukua. Tämän jälkeen ohjelma tulostaa käyttäjän syöttämien lukujen summan.
  </p>

  <p>
    Muistathan, että luvun lukeminen onnistuu Scanner-apuvälineen avulla seuraavasti:
  </p>

  <% partial 'partials/code_highlight' do %>
Scanner lukija = new Scanner(System.in);

System.out.println("Kirjoita luku ");
int luku = Integer.valueOf(lukija.nextLine());
System.out.println("Kirjoitit " + luku);
  <% end %>

  <p>
    Alla on annettuna ohjelman toivottuja esimerkkitulostuksia:
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">8</font>
    Syötä toinen luku!
    <font color="red">3</font>
    Lukujen summa on 11
  <% end %>


  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">3</font>
    Syötä toinen luku!
    <font color="red">-1</font>
    Lukujen summa on 2
  <% end %>

<% end %>

<% partial 'partials/exercise', locals: { name: 'Kolmen luvun summa', model_solution: '50224' } do %>

  <p>
    Kirjoita ohjelma, joka kysyy käyttäjältä kolmea lukua. Tämän jälkeen ohjelma tulostaa käyttäjän syöttämien lukujen summan.
  </p>

  <p>
    Alla on annettuna ohjelman esimerkkitulostuksia:
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">8</font>
    Syötä toinen luku!
    <font color="red">3</font>
    Syötä kolmas luku!
    <font color="red">3</font>
    Lukujen summa on 14
  <% end %>


  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">3</font>
    Syötä toinen luku!
    <font color="red">-1</font>
    Syötä kolmas luku!
    <font color="red">2</font>
    Lukujen summa on 4
  <% end %>

<% end %>

<p>
  Edellistä tietoa soveltamalla voimme luoda lausekkeen, joka sisältää tekstiä ja muuttujan, ja joka evaluoidaan tulostuksen yhteydessä:
</p>

<% partial 'partials/code_highlight' do %>
int x = 10;

System.out.println("muuttujan x arvo on: " + x);

int y = 5;
int z = 6;

System.out.println("y on " + y + " ja z on " + z);
<% end %>

<p>
  Tulostus:
</p>

<% partial 'partials/sample_output' do %>
muuttujan x arvo on: 10
y on 5 ja z on 6
<% end %>




<% partial 'partials/exercise', locals: { name: 'Yhteenlasku', model_solution: '50225' } do %>

  <p>
    Tee ohjelma, jonka avulla voidaan laskea kahden kokonaisluvun summa. Ohjelman alussa kysytään kahta kokonaislukua, jotka sisältävät summattavat luvut. Tämän jälkeen ohjelma tulostaa lukujen summausta kuvaavan kaavan.
  </p>

  <p>
    Tulostusesimerkkejä:
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">5</font>
    Syötä toinen luku!
    <font color="red">4</font>
    5 + 4 = 9
  <% end %>


  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">73457</font>
    Syötä toinen luku!
    <font color="red">12888</font>
    73457 + 12888 = 86345
  <% end %>

<% end %>



<% partial 'partials/exercise', locals: { name: 'Kertolasku', model_solution: '50226' } do %>

  <p>
    Tee edellistä ohjelmaa vastaava ohjelma, joka laskee kahden kokonaislukumuuttujaan sijoitetun arvon kertolaskun.
  </p>

  <p>
    Esimerkiksi jos syötetyt luvut ovat 2 ja 8, ohjelman suoritus on seuraava:
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">2</font>
    Syötä toinen luku!
    <font color="red">8</font>
    2 * 8 = 16
  <% end %>

  <p>
    Jos taas syötetyt luvut ovat 277 ja 111, ohjelman suoritus on seuraava:
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">277</font>
    Syötä toinen luku!
    <font color="red">111</font>
    277 * 111 = 30747
  <% end %>

<% end %>

<p>
  Kun olet saanut edellisen tehtävän toteutettua, kokeile mikä on suurin mahdollinen kertolasku minkä saat laskettua. Huomaamasi ilmiön taustalla on se, että kokonaislukumuuttujan arvo voi olla korkeintaan 2<sup>31</sup>-1 eli 2147483647. Tämä johtuu siitä, että kokonaislukumuuttujat esitetään tietokoneen muistissa rajatulla määrällä muistia, eli bittejä. Tähän tutustutaan tarkemmin muunmuassa kurssilla Tietokoneen toiminta.
</p>


<% partial 'partials/material_sub_heading' do %>
  Jakolasku
<% end %>


<p>
  Kokonaislukujen jakolasku on hieman hankalampi operaatio. Jakolausekkeessa käytettyjen muuttujien tyyppi määrää evaluaation tuloksena saatavan arvon tyypin. Jos kaikki jakolausekkeessa olevat muuttujat ovat kokonaislukuja, on tulos myös kokonaisluku.
</p>

<% partial 'partials/code_highlight' do %>
int tulos = 3 / 2;
System.out.println(tulos); // Huom! tulostaa 1 (kokonaisluku), sillä 3 ja 2 ovat myös kokonaislukuja
<% end %>

<% partial 'partials/code_highlight' do %>
int eka = 3:
int toka = 2;
double tulos = eka / toka;
System.out.println(tulos); // nytkin tulostus on 1, sillä eka ja toka ovat kokonaislukuja
<% end %>

<p>
  Jos jakolaskun jakaja tai jaettava (tai molemmat!) ovat liukulukuja, tulee tulokseksi myös liukuluku.
</p>

<% partial 'partials/code_highlight' do %>
double kunJaettavaOnLiukuluku = 3.0 / 2;
System.out.println(kunJaettavaOnLiukuluku); // tulostaa 1.5

double kunJakajaOnLiukuluku = 3 / 2.0;
System.out.println(kunJakajaOnLiukuluku); // tulostaa 1.5
<% end %>

<p>
  Kokonaisluku voidaan tarvittaessa muuttaa liukuluvuksi lisäämällä sen eteen tyyppimuunnosoperaatio <code>(double)</code>:
</p>

<% partial 'partials/code_highlight' do %>
int eka = 3;
int toka = 2;

double tulos1 = (double) eka / toka;
System.out.println(tulos1); // tulostaa 1.5

double tulos2 = eka / (double) toka;
System.out.println(tulos2); // tulostaa 1.5

double tulos3 = (double) (eka / toka);
System.out.println(tulos3); // tulostaa 1.0
<% end %>

<p>
  Jälkimmäisessä esimerkissä tulos pyöristyy väärin sillä laskuoperaatio kokonaisluvuilla suoritetaan ennen tyyppimuunnosta.
</p>

<p>
  Jos jakolausekkeen tulos asetetaan kokonaislukutyyppiseen muuttujaan, on tulos automaattisesti kokonaisluku.
</p>

<% partial 'partials/code_highlight' do %>
// tulos automaattisesti kokonaisluku: 1
int tulosKokonaislukuKoskaTyyppiKokonaisluku = 3.0 / 2;
<% end %>

<p>
  Seuraava esimerkki tulostaa "1.5", sillä jaettavasta tehdään liukuluku kertomalla se liukuluvulla (1.0 * 3 = 3.0) ennen jakolaskua.
</p>

<% partial 'partials/code_highlight' do %>
int jaettava = 3;
int jakaja = 2;

double tulos = 1.0 * jaettava / jakaja;
System.out.println(tulos);
<% end %>



<% partial 'partials/hint', locals: { name: 'Keskiarvon laskeminen' } do %>

  <p>
    Seuraavissa tehtävissä pyydetään laskemaan syötettyjen lukujen keskiarvo. Kerrataan peruskoulu- tai kansakoulumatematiikasta tutun keskiarvon käsite pikaisesti.
  </p>

  <p>
    Keskiarvolla tarkoitetaan lukujen summaa jaettuna niiden lukumäärällä. Esimerkiksi, jos haluaisimme lukujen 5 ja 3 keskiarvon, laskettaisiin keskiarvo kaavalla (5+3)/2. Vastaavasti, mikäli haluaisimme laskea lukujen 1, 2 ja 4 keskiarvon, laskettaisiin keskiarvo kaavalla (1+2+4)/3.
  </p>

  <p>
    Ohjelmoinnissa tähän liittyy muutamia asioita, jotka tulee muistaa. Ensiksi, nollalla jakaminen ei tyypillisesti ole sallittua. Tämä tarkoittaa sitä, että nollan luvun keskiarvon laskeminen ei onnistu. Toiseksi, mikäli ohjelma käsittelee lukujen lukumäärän ja summan kokonaislukumuuttujina, tulee muuttujista jompikumpi (tai kummatkin) muuntaa liukulukumuuttujaksi kertomalla luku arvolla 1.0 ennen jakolaskua.
  </p>

<% end %>


<% partial 'partials/exercise', locals: { name: 'Kahden luvun keskiarvo', model_solution: '50227' } do %>

  <p>
    Kirjoita ohjelma, joka kysyy käyttäjältä kahta kokonaislukua ja tulostaa lukujen keskiarvon.
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">8</font>
    Syötä toinen luku!
    <font color="red">2</font>
    Syötettyjen lukujen keskiarvo on 5.0
  <% end %>

<% end %>


<% partial 'partials/exercise', locals: { name: 'Kolmen luvun keskiarvo', model_solution: '50228' } do %>

  <p>
    Kirjoita ohjelma, joka kysyy käyttäjältä kolme kokonaislukua ja tulostaa lukujen keskiarvon.
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">8</font>
    Syötä toinen luku!
    <font color="red">2</font>
    Syötä kolmas luku!
    <font color="red">3</font>
    Syötettyjen lukujen keskiarvo on 5.5
  <% end %>


  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">9</font>
    Syötä toinen luku!
    <font color="red">5</font>
    Syötä kolmas luku!
    <font color="red">-1</font>
    Syötettyjen lukujen keskiarvo on 5.5
  <% end %>

<% end %>



<%= partial 'partials/quiz', locals: { id: '5878a2b179db890004df0d1e' } %>



<% partial 'partials/exercise', locals: { name: 'Nelilaskin', model_solution: '50229' } do %>

  <p>
    Kirjoita ohjelma, joka lukee käyttäjältä kaksi lukua ja tulostaa lukujen summan, lukujen erotuksen, lukujen kertolaskun, ja lukujen jakolaskun. Alla on kaksi esimerkkiä ohjelman toiminnasta.
  </p>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">8</font>
    Syötä toinen luku!
    <font color="red">2</font>
    8 + 2 = 10
    8 - 2 = 6
    8 * 2 = 16
    8 / 2 = 4.0
  <% end %>

  <% partial 'partials/sample_output' do %>
    Syötä ensimmäinen luku!
    <font color="red">9</font>
    Syötä toinen luku!
    <font color="red">2</font>
    9 + 2 = 11
    9 - 2 = 7
    9 * 2 = 18
    9 / 2 = 4.5
  <% end %>

<% end %>



<% partial 'partials/material_sub_heading' do %>
  Muuttujan arvoon liittyviä väärinkäsityksiä
<% end %>

<p>
  Kun tietokone suorittaa ohjelmakoodia, suorittaa se sitä käsky kerrallaan, edeten aina täsmälleen siten, kuin ohjelmakoodissa sanotaan. Kun muuttujaan asetetaan arvo, tapahtuu aina sama asia, eli yhtäsuuruusmerkin oikealla puolella oleva arvo kopioidaan yhtäsuuruusmerkin vasemmalla puolella olevan muuttujan arvoksi, eli muuttujan nimeämään paikkaan.
</p>

<p>
  On tärkeää, että ohjelmoija ymmärtää, että arvon asettaminen muuttujaan tekee aina saman asian.
</p>

<p>
  Kolme yleistä väärinkäsitystä, jotka liittyvät muuttujan arvon asettamiseen ovat seuraavat:
</p>

<ul>
  <li>Muuttujan asettamisen näkeminen siirtona kopioimisen sijaan: ohjelmakoodin <code>eka = toka</code> suorituksen jälkeen ajatellaan, että muuttujan <code>toka</code> arvo on siirtynyt muuttujan <code>eka</code> arvoksi, jonka jälkeen muuttujalla <code>toka</code> ei ole enää arvoa, tai sen arvo on esimerkiksi nolla. Tämä ei pidä paikkansa, sillä ohjelmakoodin <code>eka = toka</code> suorituksessa muuttujan <code>toka</code> nimeämässä paikassa oleva arvo kopioidaan muuttujan <code>eka</code> nimeämään paikkaan. Muuttujan <code>toka</code> arvo ei siis muutu.<br/></li>
  <li>Muuttujan asettamisen näkeminen riippuvuutena kopioimisen sijaan: ohjelmakoodin <code>eka = toka</code> suorituksen jälkeen ajatellaan, että mikä tahansa muutos muuttujaan <code>toka</code> vaikuttaa automaattisesti myös muuttujaan <code>eka</code>. Tämä ei pidä paikkansa, sillä asetus -- kopiointi -- on yksittäinen tapahtuma. Se tapahtuu vain silloin, ohjelmakoodi <code>eka = toka</code> suoritetaan.<br/></li>
  <li>Kolmas väärinkäsitys liittyy kopioimisen suuntaan: ohjelmakoodin <code>eka = toka</code> suorituksessa ajatellaan, että muuttujan <code>toka</code> arvoksi kopioidaan muuttujan <code>eka</code> arvo. Tämä näkyy myös tilanteina, missä ohjelmoija voi vahingossa kirjoittaa esimerkiksi <code>42 = arvo</code> -- onneksi ohjelmointiympäristöt tukevat myös tässä.</li>
</ul>

<p>
  Ehkäpä paras tapa tietokoneen ohjelmakoodin suorittamisen ymmärtämiseen on paperin ja kynän käyttäminen. Kun luet ohjelmakoodia, kirjoita paperille uusien muuttujien nimet, sekä kirjoita ylös rivi riviltä, miten ohjelmakoodissa olevien muuttujien arvot muuttuvat. Havainnollistetaan suoritusta seuraavalla ohjelmakoodilla:
</p>

<% partial 'partials/code_highlight' do %>
rivi 1: int eka = (1 + 1);
rivi 2: int toka = eka + 3 * (2 + 5);
rivi 3:
rivi 4: eka = 5;
rivi 5:
rivi 6: int kolmas = eka + toka;
rivi 7: System.out.println(eka);
rivi 8: System.out.println(toka);
rivi 9: System.out.println(kolmas);
<% end %>

<p>
  Alla on kirjoitettu yllä olevan ohjelmakoodin suoritus auki.
</p>

<% partial 'partials/sample_output' do %>
rivi 1: luodaan muuttuja eka
rivi 1: kopioidaan muuttujan eka arvoksi laskun 1 + 1 tulos
rivi 1: muuttujan eka arvo on 2

rivi 2: luodaan muuttuja toka
rivi 2: lasketaan 2 + 5, 2 + 5 ->  7
rivi 2: lasketaan 3 * 7, 3 * 7 -> 21
rivi 2: lasketaan eka + 21
rivi 2: kopioidaan muuttujan eka arvo laskuun, muuttujan eka arvo on 2
rivi 2: lasketaan 2 + 21, 2 + 21 -> 23
rivi 2: kopioidaan muuttujan toka arvoksi 23
rivi 2: muuttujan toka arvo on 23

rivi 3: (tyhjä, ei tehdä mitään)

rivi 4: kopioidaan muuttujan eka arvoksi 5
rivi 4: muuttujan eka arvo on 5

rivi 5: (tyhjä, ei tehdä mitään)

rivi 6: luodaan muuttuja kolmas
rivi 6: lasketaan eka + toka
rivi 6: kopioidaan muuttujan eka arvo laskuun, muuttujan eka arvo on 5
rivi 6: lasketaan 5 + toka
rivi 6: kopioidaan muuttujan toka arvo laskuun, muuttujan toka arvo on 23
rivi 6: lasketaan 5 + 23 -> 28
rivi 6: kopioidaan muuttujan kolmas arvoksi 28
rivi 6: muuttujan kolmas arvo on 28

rivo 7: tulostetaan muuttuja eka
rivi 7: kopioidaan muuttujan eka arvo tulostettavaksi, muuttujan eka arvo on 5
rivi 7: tulostetaan arvo 5

rivi 8: tulostetaan muuttuja toka
rivi 8: kopioidaan muuttujan toka arvo tulostettavaksi, muuttujan toka arvo on 23
rivi 8: tulostetaan arvo 23

rivi 9: tulostetaan muuttuja kolmas
rivi 9: kopioidaan muuttujan kolmas arvo tulostettavaksi, muuttujan kolmas arvo on 28
rivi 9: tulostetaan arvo 28
<% end %>


<p>
  Alla edellinen ohjelma askeleittain visualisoituna. Käytössä oleva askeleittainen visualisointi käsittelee ohjelmakoodia riveittäin -- pohdi askeleiden kohdalla miten ohjelma päätyy sen tulostamaan lopputulokseen.
</p>

<div class="code-states-visualizer-widget" data-input='{"code":"public class LaskentaAskeleittain {\n  public static void main(String[] args) {\n    int eka = (1 + 1);\n    int toka = eka + 3 * (2 + 5);\n\n    eka = 5;\n\n    int kolmas = eka + toka;\n    System.out.println(eka);\n    System.out.println(toka);\n    System.out.println(kolmas);\n  }\n}","stdin":"","trace":[{"stdout":"","event":"call","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"1","frame_id":1}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"2","frame_id":2}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":4,"stack_to_render":[{"func_name":"main:4","encoded_locals":{"eka":2},"ordered_varnames":["eka"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"4","frame_id":4}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":6,"stack_to_render":[{"func_name":"main:6","encoded_locals":{"eka":2,"toka":23},"ordered_varnames":["eka","toka"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"9","frame_id":9}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":8,"stack_to_render":[{"func_name":"main:8","encoded_locals":{"eka":5,"toka":23},"ordered_varnames":["eka","toka"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"12","frame_id":12}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":9,"stack_to_render":[{"func_name":"main:9","encoded_locals":{"eka":5,"toka":23,"kolmas":28},"ordered_varnames":["eka","toka","kolmas"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"17","frame_id":17}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n","event":"step_line","line":10,"stack_to_render":[{"func_name":"main:10","encoded_locals":{"eka":5,"toka":23,"kolmas":28},"ordered_varnames":["eka","toka","kolmas"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"21","frame_id":21}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n23\n","event":"step_line","line":11,"stack_to_render":[{"func_name":"main:11","encoded_locals":{"eka":5,"toka":23,"kolmas":28},"ordered_varnames":["eka","toka","kolmas"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"24","frame_id":24}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n23\n28\n","event":"step_line","line":12,"stack_to_render":[{"func_name":"main:12","encoded_locals":{"eka":5,"toka":23,"kolmas":28},"ordered_varnames":["eka","toka","kolmas"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"27","frame_id":27}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n23\n28\n","event":"return","line":12,"stack_to_render":[{"func_name":"main:12","encoded_locals":{"eka":5,"toka":23,"kolmas":28,"__return__":["VOID"]},"ordered_varnames":["eka","toka","kolmas","__return__"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"28","frame_id":28}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}}],"userlog":"Debugger VM maxMemory: 455M\n"}'></div>

<%= partial 'partials/quiz', locals: { id: '5878a3ee79db890004df0d1f' } %>
