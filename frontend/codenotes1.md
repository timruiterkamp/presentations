# Codenotes week 1

# Scope & Closures

## Compiler
* compiler heeft compiliation state
* eerst lexing = opslitsen syntax voor js
* parsen = namen geven aan stukjes coden voor code generation
* code generator = opslitten in 2, wat de engine moet lezen in compile en run time
  * var a = compile time
  * assignment = run time (a = 2)

## Rigt/left hand

```javascript
var a = leeftijd
```

* right hand side is reference ( leeftijd )
* Left hand side is declaration (var a)

* console.log() = left hand side (Vraag console met de functie log aan en de waarde in de functie)
* console.log(leeftijd) = Haal de waarde van leeftijd op om het mee tegeven aan de left hand side

* a = 23;  a en 23 Left hand side omdat het geen waarde heeft maar een harde value heeft
* a = leeftijd; a is left hand omdat het een waarde moet worden, scope a moet een waarde krijgen. Leeftijd is right hand side omdat de waarde van leeftijd moet worden opgehaald.
* b = a; b is left hand en a is right hand. De waarde van a moet weer worden opgehaald.

```javascript
function foo(a) {
    console.log(a);
}

foo (2);
```

* foo is in de function left hand omdat je een waarde ophaalt. (a) is left omdat de waarde moet worden opgehaald
* console.log(a) = right hand side omdat het moet worden opgezocht. a = right omdat het een reference is naar scope a. Het is al gedeclareerd
* foo(2) = foo is right hand side omdat de functie moet worden opgehaald . 2 left hand side omdat het statisch is.

```javascript
function foo(a) {
  var b = a;
  return a + b;
}

var c = foo(2);
```

* var c = left hand, foo(2) = right hand side omdat het refereert naar de functie
* (a) = left hand side omdat het opgehaald wordt (function foo is geen van beiden omdat het een function is)
* var b = left hand side omdat a er wordt ingehaald. a = right hand side omdat het refereert naar de waarde van de parameter
* return a = right hand side omdat het de waarde ophaalt van de parameter en b is ook right hand omdat het refereert naar de waarde van b

> Left hand side is wat moet worden opgehaald, right hand side is wat wordt gedeclareerd