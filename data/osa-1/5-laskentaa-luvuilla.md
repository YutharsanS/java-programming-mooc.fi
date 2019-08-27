---
path: "/osa-1/5-laskentaa"
# title: "Laskentaa luvuilla"
title: "Calculating with numbers"
---

<text-box variant='learningObjectives' name='Oppimistavoitteet'>

<!-- - Osaat tehdä laskutoimintoja muuttujien avulla. -->

- You know how to perform calculations with the help of variables.

<!-- - Osaat muodostaa tulostuslauseita, jossa on mukana sekä laskuoperaatioita (lausekkeita) että merkkijonoja. -->
- You can form printable statements including both calculations (expressions) and strings.

</text-box>

<!-- Laskuoperaatiot ovat tuttuja ja suoraviivaisia: yhteenlasku `+`, erotus `-`, kertolasku `*` ja jakolasku `/`. Laskentajärjestys on myös tuttu: laskenta tehdään vasemmalta oikealle sulut huomioon ottaen. Kuitenkin `*` ja `/` lasketaan ennen `+` ja `-` operaatioita, samoin kuin perus- tai kansakoulumatematiikassa on tullut tutuksi. -->

The basic mathematical operations are both familiar and straightforward: addition `+`, subtraction `-`, multiplication `*`, and division`/`. Their order follows familiar rules, too: the operations are performed from left to right, taking parentheses into account. Yet `*` and `/` precede `+` and `-`, as is familiar from elementary school mathematics.

<!-- ```java
int eka = 2;
System.out.println(eka); // tulostaa 2
int toka = 4;
System.out.println(toka); // tulostaa 4

int summa = eka + toka; // muuttujaan summa asetetaan muuttujien eka ja toka arvojen summa
System.out.println(summa); // tulostaa 6
``` -->

```java
int first = 2;
System.out.println(first); // prints 2
int second = 4;
System.out.println(second); // prints 4

int sum = first + second; // The sum of the values of the variables first and second is assigned to the variable sum
System.out.println(sum); // prints 6
```

<!-- ## Laskujärjestys ja sulut -->
## Order of operations and parentheses

<!-- Laskujärjestykseen voi vaikuttaa sulkujen avulla. Sulkujen sisällä olevat laskuoperaatiot suoritetaan ennen niiden ulkopuolella olevia laskuoperaatioita. -->

It is possible to affect the order of operations with parentheses. The operations contained within parentheses are performed before the ones outside.

<!-- ```java
int laskuSuluilla = (1 + 1) + 3 * (2 + 5);
System.out.println(laskuSuluilla); // tulostaa 23

int laskuSuluitta = 1 + 1 + 3 * 2 + 5;
System.out.println(laskuSuluitta); // tulostaa 13
``` -->

```java
int calculationWithParentheses = (1 + 1) = 3 * (2 + 5);
System.out.println(calculationWithParentheses); // prints 23

int calculationWithoutParentheses = 1 + 1 + 3 * 2 + 5;
System.out.println(calculationWithoutParentheses); // prints 13

```

<!-- Yllä olevan esimerkin voi jakaa myös osiin. -->

The example above can also be divided into steps.

<!-- ```java
int laskuSuluilla = (1 + 1);
System.out.println(laskuSuluilla); // tulostaa 2
laskuSuluilla = laskuSuluilla + 3 * (2 + 5);
System.out.println(laskuSuluilla); // tulostaa 23

int laskuSuluitta = 1 + 1;
laskuSuluitta = laskuSuluitta + 3 * 2;
laskuSuluitta = laskuSuluitta + 5;
System.out.println(laskuSuluitta); // tulostaa 13
``` -->

```java
int calculationWithParentheses = (1 + 1);
System.out.println(calculationWithParentheses); // prints 2
calculationWithParentheses = calculationWithParentheses + 3 * (2 + 5);
System.out.println(calculationWithParentheses); // prints 23

int calculationWithoutParentheses = 1 + 1;
calculationWithoutParentheses = calculationWithoutParentheses + 3 * 2;
calculationWithoutParentheses = calculationWithoutParentheses + 5;
System.out.println(calculationWithoutParentheses); // prints 13
```

<!-- <programming-exercise name="Sekunnit vuorokaudessa" tmcname='osa01-Osa01_16.SekunnitVuorokaudessa'> -->


<programming-exercise name="Seconds in a day" tmcname='part01-Part01_16.SecondsInADay'>


<!-- Toteuta tehtäväpohjaan ohjelma, joka kysyy käyttäjältä vuorokausien lukumäärää. Tämän jälkeen ohjelma tulostaa sekuntien määrän annetuissa vuorokausissa. -->

In the exercise template, implement a program that asks the user for the number of days. After this, the program prints the number of seconds in the given number of days.

<!-- Opimme aiemmin, että luvun lukeminen onnistuu seuraavasti: -->

Earlier we learned to read an integer in the following manner:

<!-- ```java
Scanner lukija = new Scanner(System.in);

System.out.println("Kirjoita luku ");
int luku = Integer.valueOf(lukija.nextLine());
System.out.println("Kirjoitit " + luku);
``` -->

```java
Scanner scanner = new Scanner(System.in);

System.out.println("Give a number:");
int number = Integer.valueOf(scanner.nextLine());
System.out.println("You gave " + number);
```

<!-- Esimerkkitulostuksia: -->

Print examples:

<!-- <sample-output>

Kuinka monen vuorokauden sekunnit tulostetaan?
**1**
86400

</sample-output> -->

<sample-output>

How many days would you like to convert to seconds?
**1**
86400

</sample-output>

<!-- <sample-output>

Kuinka monen vuorokauden sekunnit tulostetaan?
**3**
259200

</sample-output> -->

<sample-output>

How many days would you like to convert to seconds?
**3**
259200

</sample-output>

<!-- <sample-output>

Kuinka monen vuorokauden sekunnit tulostetaan?
**7**
604800

</sample-output> -->

<sample-output>

How many days would you like to convert to seconds?
**7**
604800

</sample-output>

</programming-exercise>


<quiz id="54056702-b227-5747-8d6c-d3f15e8f5c8a"></quiz>


<text-box variant='hint' name='Expression and statement'>

<!-- Lauseke (expression) on arvojen yhdistelmä, joka muuntuu arvoksi laskuoperaation tai evaluaation yhteydessä. Alla oleva lause sisältää lausekkeen `1 + 1 + 3 * 2 + 5`, joka evaluoidaan ennen arvon asetusta muuttujaan. -->
An expression is a combination of values which turns into a value when it is part of an operation or evaluated. The statement below includes the expression `1 + 1 + 3 * 2 + 5` which is evaluated before the value is assigned to the variable.

<!-- ```java
int laskuSuluitta = 1 + 1 + 3 * 2 + 5;
``` -->

```java
int calculationWithoutParentheses = 1 + 1 + 3 * 2 + 5;
```

<!-- Lausekkeen evaluaatio tapahtuu aina ennen muuttujan arvon asetusta, eli yllä lasku "1 + 1 + 3 * 2 + 5" suoritetaan ennen tuloksen asetusta muuttujaan. -->

The evaluation of an expression always precedes the placement of its value, so in the example above the calculation "1 + 1 + 3 * 2 + 5" is performed before placing the result in the variable.

</text-box>


<!-- Lausekkeen evaluointi tapahtuu ohjelmakoodissa siinä kohtaa, missä lauseke on. Evaluointi onnistuu siis esimerkiksi myös tulostuslauseen yhteydessä, jos lauseketta käytetään tulostuslauseen parametrin arvon laskemisessa. -->

The evaluation of an expression in the code occurs at the place it is written. Therefore evaluation is possible in the case of a print statement if the value of the parameter for the print statement is calculated from an expression.

<!-- ```java
int eka = 2;
int toka = 4;

System.out.println(eka + toka); // tulostaa 6
System.out.println(2 + toka - eka - toka); // tulostaa 0
``` -->

```java
int first = 2;
int second = 4;

System.out.println(first + second); // prints 6
System.out.println(2 + second - first - second); // prints 0
```

<!-- Lauseke ei muuta muuttujassa olevaa arvoa, ellei lausekkeen lopputulosta aseteta muuttujan arvoksi tai anneta parametrina esimerkiksi tulostukselle. -->

An expression does not change the value stored in a variable unless the end result is assigned to a variable or used as a parameter to printing, for instance.

<!-- ```java
int eka = 2;
int toka = 4;

// alla oleva lauseke ei edes toimi, sillä lauseketta
// ei aseteta minkään muuttujan arvoksi tai anneta parametrina
// tulostuslauseelle
eka + toka;
``` -->

```java
int first = 2;
int second = 4;

// the expression below does not even work, since
// the result is not assigned to any variable
// or given as a parameter to a print statement
first + second;
```

<quiz id="f9af4add-d06f-59bb-ab42-d1cb9733ba88"></quiz>


<!-- ## Laskentaa ja tulostamista -->
## Calculating and printing

<!-- Muuttujan arvon voi tulostaa komennolla `System.out.println`. Tulostettavaan hipsuilla merkittyyn merkkijonoon, esim. "Pituus ", voidaan lisätä muuta tulostettavaa operaation `+` avulla. -->
The command `System.out.println` prints the value of a variable. The string to be printed, which is marked by quotation marks, can be appended with the operation `+`.

<!-- ```java
int pituus = 42;
System.out.println("Pituus " + pituus);
``` -->

```java
int length = 42;
System.out.println("Length " + length);
```

<!-- <sample-output>

Pituus 42

</sample-output> -->

<sample-output>

Length 42

</sample-output>

<!-- ```java
System.out.println("tuossa on kokonaisluku -- > " + 2);
System.out.println(2 + " < -- tuossa on kokonaisluku");
```
-->

```java
System.out.println("that is an integer --> " + 2);
System.out.println(2 + " <-- that is an integer");
```


<!-- <sample-output>

tuossa on kokonaisluku -- > 2
2 <-- tuossa on kokonaisluku

</sample-output> -->

<sample-output>

that is an integer --> 2
2 <-- that is an integer

</sample-output>

<!-- Jos toinen operaation `+` kohteista on merkkijono, muutetaan myös toinen operaation kohteista merkkijonoksi ohjelman suorituksen yhteydessä. Alla olevassa esimerkissä kokonaisluku `2` on muutettu merkkijonoksi "2", ja siihen on yhdistetty merkkijono. -->

If one of the operands of the operation `+` is a string, the other operand will be changed into a string as well when the program executes. In the example below, the integer `2` is turned into the string "2", after which a string is appended to it.

<!-- Aiemmin esitellyt laskusäännöt pätevät täälläkin: -->

The rules of operation precedence apply in this context, too:

<!-- ```java
System.out.println("Neljä: " + (2 + 2));
System.out.println("Mutta! kaksikymmentäkaksi: " + 2 + 2);
``` -->

```java
System.out.println("Four: " + (2 + 2));
System.out.println("But! Twenty-two" + 2 + 2);
```

<!-- <sample-output>

Neljä: 4
Mutta! kaksikymmentäkaksi: 22

</sample-output> -->

<sample-output>

Four: 4
But! Twenty-two: 22

</sample-output>

<!-- <code-states-visualizer input='{"code":"public class Esimerkki {\n    public static void main(String[] args) {\n        System.out.println(\"Neljä: \" + (2 + 2));\n        System.out.println(\"Mutta! kaksikymmentäkaksi: \" + 2 + 2);\n    }\n}","stdin":"","trace":[{"stdout":"","event":"call","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"1","frame_id":1}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"2","frame_id":2}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Neljä: 4\n","event":"step_line","line":4,"stack_to_render":[{"func_name":"main:4","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"5","frame_id":5}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Neljä: 4\nMutta! kaksikymmentäkaksi: 22\n","event":"step_line","line":5,"stack_to_render":[{"func_name":"main:5","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"8","frame_id":8}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Neljä: 4\nMutta! kaksikymmentäkaksi: 22\n","event":"return","line":5,"stack_to_render":[{"func_name":"main:5","encoded_locals":{"__return__":["VOID"]},"ordered_varnames":["__return__"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"9","frame_id":9}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}}],"userlog":"Debugger VM maxMemory: 455M\n"}'></code-states-visualizer> -->

<code-states-visualizer input='{"code":"public class Example {\n    public static void main(String[] args) {\n        System.out.println(\"Four: \" + (2 + 2));\n        System.out.println(\"But! Twenty-two: \" + 2 + 2);\n    }\n}","stdin":"","trace":[{"stdout":"","event":"call","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"1","frame_id":1}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"2","frame_id":2}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Four: 4\n","event":"step_line","line":4,"stack_to_render":[{"func_name":"main:4","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"5","frame_id":5}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Four: 4\nBut! Twenty-two: 22\n","event":"step_line","line":5,"stack_to_render":[{"func_name":"main:5","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"8","frame_id":8}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"Four: 4\nBut! Twenty-two: 22\n","event":"return","line":5,"stack_to_render":[{"func_name":"main:5","encoded_locals":{"__return__":["VOID"]},"ordered_varnames":["__return__"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"9","frame_id":9}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}}],"userlog":"Debugger VM maxMemory: 455M\n"}'></code-states-visualizer>


<!-- <programming-exercise name="Kahden luvun summa" tmcname='osa01-Osa01_17.KahdenLuvunSumma'> -->

<programming-exercise name="Sum of two numbers" tmcname='part01-Part01_17.SumOfTwoNumbers'>

<!-- Kirjoita ohjelma, joka kysyy käyttäjältä kahta lukua. Tämän jälkeen ohjelma tulostaa käyttäjän syöttämien lukujen summan. -->

Write a program that asks the user for two numbers. After this the program prints the sum of the numbers given by the user.

<!-- Kun kysyt useampaa lukua, tee kullekin luvulle oma muuttuja: -->

When asking for multiple numbers, create a separate variable for each:

<!-- ```java
Scanner lukija = new Scanner(System.in);

System.out.println("Syötä ensimmäinen luku!");
int eka = Integer.valueOf(lukija.nextLine());
System.out.println("Syötä toinen luku!");
int toka = Integer.valueOf(lukija.nextLine());

// tee jotain luvuilla
``` -->

```java
Scanner scanner = new Scanner(System.in);

System.out.println("Give the first number:");
int first = Integer.valueOf(scanner.nextLine());
System.out.println("Give the second number:");
int second = Integer.valueOf(scanner.nextLine());

// do something with the numbers
```

<!-- Alla on annettuna ohjelman toivottuja esimerkkitulostuksia: -->

A number of expected prints from the program are given below:

<!-- <sample-output>

Syötä ensimmäinen luku!
**8**
Syötä toinen luku!
**3**
Lukujen summa on 11

</sample-output> -->

<sample-output>
̈́Give the first number:
**8**
Give the second number:
**3**
The sum of the numbers is 11
</sample-output>

<!-- <sample-output>

Syötä ensimmäinen luku!
**3**
Syötä toinen luku!
**-1**
Lukujen summa on 2

</sample-output> -->

<sample-output>

Give the first number:
**3**
Give the second number:
**-1**
The sum of the numbers is 2

</sample-output>

</programming-exercise>


<!-- <programming-exercise name="Kolmen luvun summa" tmcname='osa01-Osa01_18.KolmenLuvunSumma'> -->

<programming-exercise name="Sum of three numbers" tmcname='osa01-Osa01_18.KolmenLuvunSumma'>

<!-- Kirjoita ohjelma, joka kysyy käyttäjältä kolmea lukua. Tämän jälkeen ohjelma tulostaa käyttäjän syöttämien lukujen summan. -->

Write a program that asks the user for three numbers. After this the program prints the sum of the numbers given by the user.

<!-- Alla on annettuna ohjelman esimerkkitulostuksia: -->

A number of example print from the program are given below:

<!-- <sample-output>

Syötä ensimmäinen luku!
**8**
Syötä toinen luku!
**3**
Syötä kolmas luku!
**3**
Lukujen summa on 14

</sample-output> -->

<sample-output>

Give the first number:
**8**
Give the second number:
**3**
Give the third number:
**3**
The sum of the numbers is 14

</sample-output>

<!-- <sample-output>

Syötä ensimmäinen luku!
**3**
Syötä toinen luku!
**-1**
Syötä kolmas luku!
**2**
Lukujen summa on 4

</sample-output> -->

<sample-output>


Give the first number:
**3**
Give the second number:
**-1**
Give the third number:
**2**
The sum of the numbers is 4

</sample-output>


</programming-exercise>


<!-- Edellistä tietoa soveltamalla voimme luoda lausekkeen, joka sisältää tekstiä ja muuttujan, ja joka evaluoidaan tulostuksen yhteydessä: -->

Let's apply the previous information, and create an expression consisting some text and a variable that is evaluated at the time of printing:

<!-- ```java
int x = 10;

System.out.println("muuttujan x arvo on: " + x);

int y = 5;
int z = 6;

System.out.println("y on " + y + " ja z on " + z);
``` -->

```java
int x = 10;

System.out.println("The value of the variable x is: " + x);

int y = 5;
int z = 6;

System.out.println("y is " + y + " and z is " + z);
```

<!-- Tulostus: -->

The print:

<!-- <sample-output>

muuttujan x arvo on: 10
y on 5 ja z on 6

</sample-output> -->


<sample-output>

The value of the variable x is: 10
y is 5 and z is 6

</sample-output>


<!-- <programming-exercise name="Yhteenlasku ja kaava" tmcname='osa01-Osa01_19.YhteenlaskuJaKaava'> -->

<programming-exercise name="Addition formula" tmcname='part01-Part01_19.AdditionFormula'>


<!-- TODO: tarkenna tehtävänantoa (myös kaava)
Tee ohjelma, jonka avulla voidaan laskea kahden kokonaisluvun summa. Ohjelman alussa kysytään kahta kokonaislukua, jotka sisältävät summattavat luvut. Tämän jälkeen ohjelma tulostaa lukujen summausta kuvaavan kaavan. -->

TODO: specify the assignment (the formula, too)
Create a program that can be used the add together two integers. At the beginning two integers (to be summed) are asked from the user. After this the program prints the formula that describes the addition of the numbers.


<!-- Tulostusesimerkkejä: -->

Print examples:

<!-- <sample-output>

Syötä ensimmäinen luku!
**5**
Syötä toinen luku!
**4**
5 + 4 = 9

</sample-output> -->

<sample-output>

Give the first number:
**5**
Give the second number:
**4**
5 + 4 = 9

</sample-output>

<!-- <sample-output>

Syötä ensimmäinen luku!
**73457**
Syötä toinen luku!
**12888**
73457 + 12888 = 86345

</sample-output> -->

<sample-output>

Give the first number:
**73457**
Give the second number:
**128888**
73457 + 12888 = 86345

</sample-output>

</programming-exercise>


<!-- <programming-exercise name="Kertolasku ja kaava" tmcname='osa01-Osa01_20.KertolaskuJaKaava'> -->

<programming-exercise name="Multiplication formula" tmcname='part01-Part01_20.MultiplicationFormula'>


<!-- Tee edellistä ohjelmaa mukaillen ohjelma, joka laskee kahden kokonaislukumuuttujaan sijoitetun arvon kertolaskun. -->

Similar to the previous exercise, create a program that multiplies the values stored in two integer variables.

<!-- Esimerkiksi jos syötetyt luvut ovat 2 ja 8, ohjelman suoritus on seuraava: -->

For instance, if the entered numbers are 2 and 8, the program should print the following:

<!-- <sample-output>

Syötä ensimmäinen luku!
**2**
Syötä toinen luku!
**8**
2 * 8 = 16

</sample-output> -->

<sample-output>

Give the first number:
**2**
Give the second number:
**8**
2 * 8 = 16

</sample-output>

<!-- Jos taas syötetyt luvut ovat 277 ja 111, ohjelman suoritus on seuraava: -->

On the other hand, if the entered numbers are 277 and 111, the print should be the following:

<!-- <sample-output>

Syötä ensimmäinen luku!
**277**
Syötä toinen luku!
**111**
277 * 111 = 30747

</sample-output> -->

<sample-output>

Give the first number:
**277**
Give the second number:
**111**
277 * 111 = 30747

</sample-output>

</programming-exercise>

TODO: miksi alla oleva teksti näkyy pienellä?

<!-- Kun olet saanut edellisen tehtävän toteutettua, kokeile mikä on suurin mahdollinen kertolasku minkä saat laskettua. Huomaamasi ilmiön taustalla on se, että kokonaislukumuuttujan arvo voi olla korkeintaan 2<sup>31</sup>-1 eli 2147483647. Tämä johtuu siitä, että kokonaislukumuuttujat esitetään tietokoneen muistissa 32 bitin avulla. Tähän tutustutaan tarkemmin muunmuassa kurssilla Tietokoneen toiminta. -->

Once you have completed the previous exercise, try out which is the greatest possible multiplication you can calculate. The background for the phenomenon you noticed is that the value of an integer value is capped at the maximum of 2<sup>31</sup>-1 (i.e. 2147483647). This owes to the fact that integer variables are represented with 32 bits in the memory of the computer. The representation of variables is explained in more detail on the course Computer Organization, among others.


<!-- ## Jakolasku -->

## Division

<!-- Kokonaislukujen jakolasku on hieman hankalampi operaatio. Jakolausekkeessa käytettyjen muuttujien tyyppi määrää evaluaation tuloksena saatavan arvon tyypin. Jos kaikki jakolausekkeessa olevat muuttujat ovat kokonaislukuja, on tulos myös kokonaisluku. -->

Division is a slightly trickier operation. The types of the variables that take part in the division decide the type of the result gained by executing the command. If all the variables in the division are integers, the result of that calculation is an integer, too.

<!-- ```java
int tulos = 3 / 2;
System.out.println(tulos);
``` -->

```java
int result = 3 / 2;
System.out.println(result);
```

<sample-output>

1

</sample-output>

<!-- Edellinen esimerkki tulostaa luvun 1, sillä 3 ja 2 ovat kokonaislukuja ja kahden kokonaisluvun jakolaskun tulos on kokonaisluku. -->

The previous example prints 1: both 3 and 2 are integers, and the division of two integers always produces an integer.

<!-- ```java
int eka = 3;
int toka = 2;
double tulos = eka / toka;
System.out.println(tulos);
``` -->

```java
int first = 3;
int second = 2;
double result = first / second;
System.out.println(result);
```

<sample-output>

1

</sample-output>

<!-- Nytkin tulostus on 1, sillä eka ja toka ovat (yhä) kokonaislukuja. -->

The print is 1 also in this case, since first and second are integers.

<!-- Jos jakolaskun jakaja tai jaettava (tai molemmat!) ovat liukulukuja, tulee tulokseksi myös liukuluku. -->

If the dividend or divisor (or both!) of the division is a floating point number, the result is a floating point number as well.

<!-- ```java
double kunJaettavaOnLiukuluku = 3.0 / 2;
System.out.println(kunJaettavaOnLiukuluku); // tulostaa 1.5

double kunJakajaOnLiukuluku = 3 / 2.0;
System.out.println(kunJakajaOnLiukuluku); // tulostaa 1.5
``` -->

```java
double whenDividendIsFloat = 3.0 / 2;
System.out.println(whenDividendIsFloat); // prints 1.5

double whenDivisorIsFloat = 3 / 2.0;
System.out.println(whenDivisorIsFloat); // prints 1.5
```


<sample-output>

1.5
1.5

</sample-output>

<!-- Kokonaisluku voidaan tarvittaessa muuttaa liukuluvuksi lisäämällä sen eteen tyyppimuunnosoperaatio `(double)`: -->

An integers can be converted into a floating point number by preceding it by the type casting operation `(double)`:

<!-- ```java
int eka = 3;
int toka = 2;

double tulos1 = (double) eka / toka;
System.out.println(tulos1); // tulostaa 1.5

double tulos2 = eka / (double) toka;
System.out.println(tulos2); // tulostaa 1.5

double tulos3 = (double) (eka / toka);
System.out.println(tulos3); // tulostaa 1.0
``` -->

```java
int first = 3;
int second = 2;

double result1 = (double) first / second;
System.out.println(result1); // prints 1.5

double result2 = first / (double) second;
System.out.println(result2); // prints 1.5

double result3 = (double) (first / second);
System.out.println(result3); // prints 1.0
```

<sample-output>

1.5
1.5
1.0

</sample-output>


<!-- Jälkimmäisessä esimerkissä tulos pyöristyy väärin sillä laskuoperaatio kokonaisluvuilla suoritetaan ennen tyyppimuunnosta. -->

The last example produces an incorrectly rounded result, because the division with integers is executed before the type casting.

<!-- Jos jakolausekkeen tulos asetetaan kokonaislukutyyppiseen muuttujaan, on tulos automaattisesti kokonaisluku. -->

If the result of a division is placed into an integer-type variable, the result is automatically an integer.

<!-- ```java
int kokonaisluku = 3.0 / 2;
System.out.println(kokonaisluku);
``` -->

```java
int integer = 3.0 / 2;
System.out.println(integer);
```

<sample-output>

1

</sample-output>

<!-- Seuraava esimerkki tulostaa "1.5", sillä jaettavasta tehdään liukuluku kertomalla se liukuluvulla (1.0 * 3 = 3.0) ennen jakolaskua. -->

The next example prints "1.5"; the dividend is converted into a floating-point number by multiplying it with a floating point number prior to executing the division.

<!-- ```java
int jaettava = 3;
int jakaja = 2;

double tulos = 1.0 * jaettava / jakaja;
System.out.println(tulos);
``` -->

```java
int dividend = 3;
int divisor = 2;

double result = 1.0 * dividend / divisor;
System.out.println(result);
```

<sample-output>

1.5

</sample-output>


<!-- <text-box variant='hint' name='Keskiarvon laskeminen'> -->

<text-box variant='hint' name='Calculating the average'>


<!-- Seuraavissa tehtävissä pyydetään laskemaan syötettyjen lukujen keskiarvo. Kerrataan peruskoulu- tai kansakoulumatematiikasta tutun keskiarvon käsite pikaisesti. -->

The next exercises task you with calculating the average of the entered numbers. Let's briefly review the notion of average, which is familiar from elementary school mathematics.

<!-- Keskiarvolla tarkoitetaan lukujen summaa jaettuna niiden lukumäärällä. Esimerkiksi, jos haluaisimme lukujen 5 ja 3 keskiarvon, laskettaisiin keskiarvo kaavalla (5+3)/2. Vastaavasti, mikäli haluaisimme laskea lukujen 1, 2 ja 4 keskiarvon, laskettaisiin keskiarvo kaavalla (1+2+4)/3. -->

An average refers to the sum of numbers divided by their count. For instance, the average of the numbers 5 and 3 can be calculated with the formula (5+3)/2. Similarly, the average of the numbers 1, 2, and 4 is produced by the formula (1+2+4)/3.

<!-- Ohjelmoinnissa tähän liittyy muutamia asioita, jotka tulee muistaa. Ensiksi, nollalla jakaminen ei tyypillisesti ole sallittua. Tämä tarkoittaa sitä, että nollan luvun keskiarvon laskeminen ei onnistu. Toiseksi, mikäli ohjelma käsittelee lukujen lukumäärän ja summan kokonaislukumuuttujina, tulee muuttujista jompikumpi (tai kummatkin) muuntaa liukulukumuuttujaksi kertomalla luku arvolla 1.0 ennen jakolaskua. -->

In the context of programming there are a few things to remember. Firstly, dividing by zero is typically not permitted. This implies that calculating the average of zero numbers is impossible. Secondly, the program might handle both the sum of the numbers and their total count as integers; in such a case one of them (or both) should be converted into a floating point number by dividing it by 1.0 before executing the division.

</text-box>


<!-- <programming-exercise name="Kahden luvun keskiarvo" tmcname='osa01-Osa01_21.KahdenLuvunKeskiarvo'> -->

<programming-exercise name="Average of two numbers" tmcname='part01-Part01_21.AverageOfTwoNumbers'>


<!-- Kirjoita ohjelma, joka kysyy käyttäjältä kahta kokonaislukua ja tulostaa lukujen keskiarvon. -->

Write a program that asks the user for two integers and prints their average.

<!-- <sample-output>

Syötä ensimmäinen luku!
**8**
Syötä toinen luku!
**2**
Syötettyjen lukujen keskiarvo on 5.0

</sample-output> -->

<sample-output>

Give the first number:
**8**
Give the second number:
**2**
The average is 5.0

</sample-output>

</programming-exercise>


<!-- <programming-exercise name="Kolmen luvun keskiarvo"  tmcname='osa01-Osa01_22.KolmenLuvunKeskiarvo'> -->

<programming-exercise name="Average of three numbers"  tmcname='part01-Part01_22.AverageOfThreeNumbers'>


<!-- Kirjoita ohjelma, joka kysyy käyttäjältä kolme kokonaislukua ja tulostaa lukujen keskiarvon. -->

Write a program that asks the user for three integers and prints their average.


<!-- <sample-output>

Syötä ensimmäinen luku!
**8**
Syötä toinen luku!
**2**
Syötä kolmas luku!
**3**
Syötettyjen lukujen keskiarvo on 4.333333333333333

</sample-output> -->

<sample-output>

Give the first number:
**8**
Give the second number:
**2**
Give the third number:
**3**
The average is 4.333333333333333

</sample-output>

<!-- <sample-output>

Syötä ensimmäinen luku!
**9**
Syötä toinen luku!
**5**
Syötä kolmas luku!
**-1**
Syötettyjen lukujen keskiarvo on 4.333333333333333

</sample-output> -->

<sample-output>

Give the first number:
**9**
Give the second number:
**5**
Give the third number:
**-1**
The average is 4.333333333333333

</sample-output>

</programming-exercise>


<quiz id="cff67523-26f0-5f35-b00f-070778b40541"></quiz>


<!-- <programming-exercise name="Nelilaskin" tmcname='osa01-Osa01_23.Nelilaskin'> -->

<programming-exercise name="Simple calculator" tmcname='part01-Part01_23.Simple calculator'>


<!-- Kirjoita ohjelma, joka lukee käyttäjältä kaksi lukua ja tulostaa lukujen summan, lukujen erotuksen, lukujen kertolaskun, ja lukujen jakolaskun. Alla on kaksi esimerkkiä ohjelman toiminnasta. -->

Write a program that reads two numbers from the user and prints their sum, difference, product, and quotient. Two examples of the execution of the program are supplied below.

<!-- <sample-output>

Syötä ensimmäinen luku!
**8**
Syötä toinen luku!
**2**
8 + 2 = 10
8 - 2 = 6
8 * 2 = 16
8 / 2 = 4.0

</sample-output> -->

<sample-output>

Give the first number:
**8**
Give the second number:
**2**
8 + 2 = 10
8 - 2 = 6
8 * 2 = 16
8 / 2 = 4.0

</sample-output>


<sample-output>

Give the first number:
**9**
Give the second number:
**2**
9 + 2 = 11
9 - 2 = 7
9 * 2 = 18
9 / 2 = 4.5

</sample-output>



</programming-exercise>


<!-- ## Muuttujan arvoon liittyviä väärinkäsityksiä -->

## Misunderstandings about the value of a variable

<!-- Kun tietokone suorittaa ohjelmakoodia, suorittaa se sitä käsky kerrallaan, edeten aina täsmälleen siten, kuin ohjelmakoodissa sanotaan. Kun muuttujaan asetetaan arvo, tapahtuu aina sama asia, eli yhtäsuuruusmerkin oikealla puolella oleva arvo kopioidaan yhtäsuuruusmerkin vasemmalla puolella olevan muuttujan arvoksi, eli muuttujan nimeämään paikkaan. -->

When executing the program code, the computer executes it one command at a time, always advancing exactly in the manner specified by the code. When a value is place into a variable, the same chain of events always occurs: the value on the right side of the equality sign is copied to serve as the value of the variable on the left side (i.e. copied to the location specified by that variable).

<!-- On tärkeää, että ohjelmoija ymmärtää, että arvon asettaminen muuttujaan tekee aina saman asian. -->

It is crucial for programmers to understand that assigning a value to a varibale always occurs in the same way.

<!-- Kolme yleistä väärinkäsitystä, jotka liittyvät muuttujan arvon asettamiseen ovat seuraavat: -->

What follows is three common misunderstanding about assigning a value to a variable:

<!-- * Muuttujan asettamisen näkeminen siirtona kopioimisen sijaan: ohjelmakoodin `eka = toka` suorituksen jälkeen ajatellaan, että muuttujan `toka` arvo on siirtynyt muuttujan `eka` arvoksi, jonka jälkeen muuttujalla `toka` ei ole enää arvoa, tai sen arvo on esimerkiksi nolla. Tämä ei pidä paikkansa, sillä ohjelmakoodin `eka = toka` suorituksessa muuttujan `toka` nimeämässä paikassa oleva arvo kopioidaan muuttujan `eka` nimeämään paikkaan. Muuttujan `toka` arvo ei siis muutu. -->

* Assigning a value is viewed as a transfer instead of a copy operation: after executing `first = second` it is thought that the value of the variable `second` has been moved to the value of the variable `first`. Afterwards the variable `second` no longer has a value, or its value is e.g. 0. This is incorrect; in executing `first = second`,  the value in the position specified by `second` is copied to the place specified by the variable `first`. The value of the variable `second` is therefore not modified.

<!-- * Muuttujan asettamisen näkeminen riippuvuutena kopioimisen sijaan: ohjelmakoodin `eka = toka` suorituksen jälkeen ajatellaan, että mikä tahansa muutos muuttujaan `toka` vaikuttaa automaattisesti myös muuttujaan `eka`. Tämä ei pidä paikkansa, sillä asetus -- kopiointi -- on yksittäinen tapahtuma. Se tapahtuu vain silloin, kun ohjelmakoodi `eka = toka` suoritetaan. -->

* Assigning a value is viewed as creating a dependency instead of a copy operation: after executing `first = second` it is thought that any change in the value of the variable `second` is also automatically reflected in the value of the variable `first`. This is incorrect; assignment -- i.e. copying -- is a one-time event. It only occurs when the program code `first = second` is executed.

<!-- * Kolmas väärinkäsitys liittyy kopioimisen suuntaan: ohjelmakoodin `eka = toka` suorituksessa ajatellaan, että muuttujan `toka` arvoksi kopioidaan muuttujan `eka` arvo. Tämä näkyy myös tilanteina, missä ohjelmoija voi vahingossa kirjoittaa esimerkiksi `42 = arvo` -- onneksi ohjelmointiympäristöt tukevat myös tässä. -->

* The third misunderstanding concerns the direction of the copying: it is thought that in the execution of the code `first = second` the value of the variable `first` is set as the value of the variable `second`. The misunderstanding may cause situations where the programmer accidentally writes e.g. `42 = value -- fortunately the IDEs support the programmer in this issue, too.

<!-- Ehkäpä paras tapa tietokoneen ohjelmakoodin suorittamisen ymmärtämiseen on paperin ja kynän käyttäminen. Kun luet ohjelmakoodia, kirjoita paperille uusien muuttujien nimet, sekä kirjoita ylös rivi riviltä, miten ohjelmakoodissa olevien muuttujien arvot muuttuvat. Havainnollistetaan suoritusta seuraavalla ohjelmakoodilla: -->

Perhaps the best method to understand the execution of program code is to use pen and paper. When reading program code, write down on paper the names of the new variables. Track also how the values of the variables in the code change, row by row. Let's demonstate the execution with the following program code:

<!-- ```java
rivi 1: int eka = (1 + 1);
rivi 2: int toka = eka + 3 * (2 + 5);
rivi 3:
rivi 4: eka = 5;
rivi 5:
rivi 6: int kolmas = eka + toka;
rivi 7: System.out.println(eka);
rivi 8: System.out.println(toka);
rivi 9: System.out.println(kolmas);
``` -->

```java
rivi 1: int first = (1 + 1);
rivi 2: int second = first + 3 * (2 + 5);
rivi 3:
rivi 4: first = 5;
rivi 5:
rivi 6: int third = first + second;
rivi 7: System.out.println(first);
rivi 8: System.out.println(second);
rivi 9: System.out.println(third);
```

<!-- Alla on kirjoitettu yllä olevan ohjelmakoodin suoritus auki. -->

Below the execution of the code above has been explained with writing.

<!-- <sample-output>

rivi 1: luodaan muuttuja eka
rivi 1: kopioidaan muuttujan eka arvoksi laskun 1 + 1 tulos
rivi 1: muuttujan eka arvo on 2
rivi 2: luodaan muuttuja toka
rivi 2: lasketaan 2 + 5, 2 + 5 -> 7
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
rivi 7: tulostetaan muuttuja eka
rivi 7: kopioidaan muuttujan eka arvo tulostettavaksi, muuttujan eka arvo on 5
rivi 7: tulostetaan arvo 5
rivi 8: tulostetaan muuttuja toka
rivi 8: kopioidaan muuttujan toka arvo tulostettavaksi, muuttujan toka arvo on 23
rivi 8: tulostetaan arvo 23
rivi 9: tulostetaan muuttuja kolmas
rivi 9: kopioidaan muuttujan kolmas arvo tulostettavaksi, muuttujan kolmas arvo on 28
rivi 9: tulostetaan arvo 28

</sample-output> -->

<sample-output>

row 1: create variable first
row 1: copy the result of the calculation 1 + 1 and place as the value of the variable
row 1: the value of the variable first is 2
row 2: create variable second
row 2: calculate 2 + 5, 2 + 5 -> 7
row 2: calculate 3 * 7, 3 * 7 -> 21
row 2: calculate first + 21
row 2: copy the value of the variable first into the calculation, that value is 2
row 2: calculate 2 + 21, 2 + 21 -> 23
row 2: copy 23 to the value of the variable second
row 2: the value of the variable second is 23
row 3: (empty, do nothing)
row 4: copy 5 to the value of the variable first
row 4: the value of the variable first is 5
row 5: (empty, do nothing)
row 6: create variable third
row 6: calculate first + second
row 6: copy the value of the variable first into the calculation, that value is 5
row 6: calculate 5 + second
row 6: copy the value of the variable second into the calculation, that value is 23
row 6: calculate 5 + 23 -> 28
row 6: copy 28 to the value of the variable third
row 6: the value of the variable third is 28
row 7: print variable first
row 7: copy the value of the variable first for print operation, that value is 5
row 7: print value 5
row 8: print variable second
row 8: copy the value of the variable second for print operation, that value is 23
row 8: print value 23
row 9: print variable third
row 9: copy the value of the variable third for print operation, that value is 28
row 9: print value 28

</sample-output>

<!-- Alla edellinen ohjelma askeleittain visualisoituna. Käytössä oleva askeleittainen visualisointi käsittelee ohjelmakoodia riveittäin -- pohdi askeleiden kohdalla miten ohjelma päätyy sen tulostamaan lopputulokseen. -->

Below is the previous program visualized in steps. The staged visualization in use processes the program code in rows -- on every step reflect on how the program ends up with the result that it prints.

<code-states-visualizer input='{"code":"public class CalculationInSteps {\n  public static void main(String[] args) {\n    int first = (1 + 1);\n    int second = first + 3 * (2 + 5);\n\n    first = 5;\n\n    int third = first + second;\n    System.out.println(first);\n    System.out.println(second);\n    System.out.println(third);\n  }\n}","stdin":"","trace":[{"stdout":"","event":"call","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"1","frame_id":1}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":3,"stack_to_render":[{"func_name":"main:3","encoded_locals":{},"ordered_varnames":[],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"2","frame_id":2}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":4,"stack_to_render":[{"func_name":"main:4","encoded_locals":{"first":2},"ordered_varnames":["first"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"4","frame_id":4}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":6,"stack_to_render":[{"func_name":"main:6","encoded_locals":{"first":2,"second":23},"ordered_varnames":["first","second"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"9","frame_id":9}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":8,"stack_to_render":[{"func_name":"main:8","encoded_locals":{"first":5,"second":23},"ordered_varnames":["first","second"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"12","frame_id":12}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"","event":"step_line","line":9,"stack_to_render":[{"func_name":"main:9","encoded_locals":{"first":5,"second":23,"third":28},"ordered_varnames":["first","second","third"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"17","frame_id":17}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n","event":"step_line","line":10,"stack_to_render":[{"func_name":"main:10","encoded_locals":{"first":5,"second":23,"third":28},"ordered_varnames":["first","second","third"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"21","frame_id":21}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n23\n","event":"step_line","line":11,"stack_to_render":[{"func_name":"main:11","encoded_locals":{"first":5,"second":23,"third":28},"ordered_varnames":["first","second","third"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"24","frame_id":24}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n23\n28\n","event":"step_line","line":12,"stack_to_render":[{"func_name":"main:12","encoded_locals":{"first":5,"second":23,"third":28},"ordered_varnames":["first","second","third"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"27","frame_id":27}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}},{"stdout":"5\n23\n28\n","event":"return","line":12,"stack_to_render":[{"func_name":"main:12","encoded_locals":{"first":5,"second":23,"third":28,"__return__":["VOID"]},"ordered_varnames":["first","second","third","__return__"],"parent_frame_id_list":[],"is_highlighted":true,"is_zombie":false,"is_parent":false,"unique_hash":"28","frame_id":28}],"globals":{},"ordered_globals":[],"func_name":"main","heap":{}}],"userlog":"Debugger VM maxMemory: 455M\n"}'></code-states-visualizer>

<quiz id="286b44eb-0a4f-51de-9c67-68d5351a3b37"></quiz>