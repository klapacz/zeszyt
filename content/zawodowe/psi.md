---
title: PSI
description: Projektowanie Stron Internetowych
---


## Lekcja organizacyjna

Zapoznanie się z:
- PSO
- regulaminem pracowni komputerowej
- programem nauczania

## HTML, szablon strony

> HTML - Hyper Text Markup Language (Hipertekstowy język znaczników)

Język HTML jest zbiorem znaczników (tagów) które są odpowiednio interpretowane przez przeglądarkę. 


Tag (znacznik) HTML:
```html
<tag atrybut="wartość">Zawartość</tag>

na przykład:
<button type="submit">wykonaj</button>

komentarze są ignorowane przez przeglądarkę:
<!-- tekst komentarza -->
```

Szablon strony (część tagów opcjonalna)
```html
<!DOCTYPE html> <!-- Znacznik opisujący wersję użytego HTMLa, w tym przypadku najnowszy HTML 5  -->
<html lang="en"> <!-- Główny tag, w którym zawiera się cała strona -->
<head> <!-- zawartość head jest nie widoczna -->
    <meta charset="UTF-8"> <!-- zapewnia poprawne wyświetlanie tekstu (np. polskie znaki) -->
    <title>Document</title> <!-- tytuł strony, wyświetla się na pasku zakładek -->
    <meta name="keywords" content="słowa kluczowe"> <!-- słowa kluczowe, używane przez wyszukiwarkę -->
    <meta name="author" content="Imię Nazwisko"> <!-- autor strony… -->
</head>
<body>
    <!-- zawartość strony -->
</body>
</html>
```

najczęściej używane tagi (należy umieścć w sekcji `body`): 
```html
<div>Podstawowy element strony</div>
<h1>Nagłówek pierwszego stopnia, istnieją nagłówki 1-6 <h1>`
<p>paragraf (akapit)</p>
<i>italic text, pochylony</i>
<b>bold text, pogrubiony</b>
```

## Wprowadzenie do PHP

PHP to skryptowy język wykonywany po stronie serwer (interpreterem nie jest przeglądarka tylko serwer). Kod PHP jest nie jawny osoba odwiedzająca stronę nie może go zobaczyć, do użytkownika dociera tylko wygenerowany HTML. Jako serwer można wykorzystać na przykład [XAMPP](https://www.apachefriends.org/index.html), po zainstalowaniu należy uruchomić `C:\xampp\xampp-control.exe` i włączyć serwer [Apache](https://en.wikipedia.org/wiki/Apache_HTTP_Server). Stronę umieszczamy w katalogu `C:\xampp\htdocs`. Strona główna zawiera się w pliku `index.php`. Strona serwowana będzie pod adresem `localhost` (inaczej `127.0.0.1`)

> Alternatywnie można uruchomić [serwer developerki PHP](https://www.php.net/manual/en/features.commandline.webserver.php) w dowolnym folderze komendą `php -S localhost:8080` i w przeglądarce przejść pod adres `localhost:8080`

Skrypty PHP mają rozszerzenie `.php`. Można wpisywać w nich HTML.

```phtml
<h1 id="first-heading">HTML w PHP!!!</h1>
```

Kod PHP umieszcza się w specjalnych znacznikach, otwierającym `<?php` i zamykającym `?>`

```phtml
HTML robi <br><br><br><br>

<?php
// Tutaj Wpisuje się kod PHP, tak wygląda komentarz - jest ignorowany przez interpreter
?>

<p> tu może bć dalej HTML </p>
```

Można też użyć tylko tagu otwierającego `<?php` na początku pliku i nie zamykać go, wtedy cały plik będzie wykonywany jako kod PHP.

Każda linia kodu w php __musi kończyć się `;`__

### Zmienne

Zmienna przechowuje wartość, na przykład ciąg znaków (*string*), liczbę. Wartość zmiennej można zmieniać podczas wykonywania skryptu. Nazwa zmiennej musi zaczynać się od `$`, może zawierać liczby, litery i `_`.

przykłady
```phtml
<?php
$a = 10;
$b = 10;

$c = $a * $b; // wartość $c to 100
```

#### Typy zmiennych, działania na zmiennych

string - ciąg znaków.

```phtml
<?php
$number = 10;
$string = 'jakis tekst';

$biggerNumber = $number * 10; // 100;
$number = $number + 1; // 11
$number++; // 12, inkramentacja (zwiększenie wartości o jeden), działa tak samo jak linijka wyżej


$newString = $string . ' i więcej tekstu i liczba ' . $number;
/* 
    wynik: 'jakiś tekst i więcej tekstu i więcej tekstu i liczba 12'
    Operator kropki łączy stringi (ciągi znaków)
    Tak wygląda komentarz wieloliniowy.
*/
```

### Wyświetlanie na stronie
```phtml
<?php
echo $zmienna;
print($zmienna)
?>

<div>kod HTML może być pomiędzy różnymi tagami PHP </div>

<?= $zmienna ?>
```
> Istnieje tag PHP dedykowany do przekazywania treści na stronę, otwiera się go `<?=` i zamyka standardowo dla PHP `?>`
> ```phtml
> <?php $a = 10; $b = 20; ?>
> <?= $a + $b ?> // 30
> <?= 'Hello from PHP' ?>
> ```

> Można zapisać parę "linijek" obok siebie, dla interpretera ważne są `;`, nie znaki nowej lini
> ```phtml
> <?php
> $zmienna = 'tekst';
> echo $zmienna;
> ?>
> zadziała tak samo jak
> <?php $zmienna = 'tekst'; echo $zmienna; ?>
> ```

## PHP - Instrukcja warunkowa `if`

Instrukcję `if` wykorzystujemy wtedy gdy do wykonania działania potrzebne jest spełnienie jakiegoś warunku.

Składnia instrukcji `if`

```phtml
<?php

if(true) {
	// code …
} elseif (true) {
	// wykona się jeśli warunek z pierwszego `if` zwróci `false` i warunek z `elseif` zwróci `true`
	// można wstawić wiele elseif, wykonają się tylko jeśli żaden poprzedni się nie wykonał
} else {
	// wykona się jeśli wszystkie poprzednie zwrócą `false`
}

```

Jeżeli chcemy sprawdzić czy zmienna jest równa jakiejś wartości bądź ciąg znaków używamy `==`.

Przykłady

```phtml
<?php
if($a > 0) echo 'jestem większa od zera';
elseif($a < 0) echo 'jestem mniejsza od zera';
else echo 'jestem równa zero';
```

## Tabelki HTML

Znaczniki do konstruowania tabelki
- `<table>` - główny element zagnieżdżamy w nim całą tabelkę
- `<thead>` - nagłówek tabeli
- `<tbody>` - ciało tabeli
- `<tr>`  - table row, rząd, zagnieżdżamy w `<thead>` lub `<tbody>`
- `<th>` - komórka tabeli, będąca nagłówkiem, **najczęściej** zagnieżdżamy w tagu `<tr>` znajdującym się w `<thead>`
- `<td>` - komórka tabeli w `<tbody>`, zagnieżdżamy w tagu `<tr>` znajdującym się w `<tbody>`

Atrybuty elementów `<th>` i `<td>`
  - `colspan="2"` - "łączy" komórkę z komórką położoną po prawej
  - `rowspan="2"` - "łączy" komórkę z komórką znajdującą się poniżej
  - `border` - nie powinno się używać, ale pani każe, tworzy obramowanie

Przykłady
```html
<table>
    <thead>
        <tr>
            <th colspan="2">The table header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
        </tr>
    </tbody>
</table>
```
wynik (+ stylowanie z mojej strony)
<table>
    <thead>
        <tr>
            <th colspan="2">The table header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
        </tr>
    </tbody>
</table>

## HTML formularze

Formularze umożliwiają wprowadzenie różnego rodzaju danych na stronę oraz opcjonalne przekazanie ich do serwera (maila).

sposób przekazania na maila `[action="mailto:mail@address.com]`.

```html
<form action="link-do-wykonania" method="metoda-http">
	<input type="text|password|button|checkbox|color|date|email|file|number-domyślnie-text" value="wartość" maxlength="maksymalny-rozmiar-pola" placeholder="Wpisz hasło…">

	Podaj płeć
  	<input type="radio" name="sex" value="male"> Mężczyzna  
  	<input type="radio" name="sex" value="female"> Kobieta


	<select name="pets">
		<option value="dog">Dog</option>
		<option value="cat">Cat</option>
		<option value="hamster">Hamster</option>
		<option value="parrot">Parrot</option>
		<option value="spider">Spider</option>
		<option value="goldfish">Goldfish</option>
	</select>
	<textarea></textarea>
</form>
```

## przechwytywanie w PHP zawartości formularza

```phtml
<form method="POST">
    <input name="username"> <!-- type="text" jest wartością domyślną, po atrybucie name odnosimy się w php -->
    <button type="submit">Wyślij</button>
</form>

<?php
if(isset($_POST['username'])) { // sprawdzamy czy użytkownik nas nie troluje i wyslał coś w formularzu
    $username = $_POST['username'];
    echo $a;
}
```

## PHP Pętla for

```phtml
<?php

for($i = 0; $i < 10; i++) {
    echo "ZST";
}
?>

<?php for($i = 0; $i < 10; i++): ?>
    ZST <br>
<?php endif; ?>
```

## HTML odsyłacze

Odsyłacze umożliwiają powiązanie między dokumentami, często nazywane są hiperłączami.

```html
<a href="about-me.html">Website</a> <!-- relative path / ścieżka względna -->
<a href="/about-me.html">Website</a> <!-- absolut path / ścieżka bezwzględna -->
<a href="https://example.com">Website</a>
<a href="https://example.com" target="_blank">Website</a> <!-- W nowej karcie -->
<a href="mailto:m.bluth@example.com">Email</a>
<a href="tel:+123456789">Phone</a>
```

Etykiety zwane często zakładkami lub kotwicami, pozwalają na szybkie przemieszczanie się do konkretnego miejsca w tekście

```html
<a href="#id"> Link to id </a>
```