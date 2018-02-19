# Codenotes week 1

## Scope & Closures

## Compiler

* compiler heeft compiliation state
* eerst lexing = opslitsen syntax voor js
* parsen = namen geven aan stukjes coden voor code generation
* code generator = opslitten in 2, wat de engine moet lezen in compile en run time
  * var a = compile time
  * assignment = run time (a = 2)

## Rigt/left hand

```javascript
var a = leeftijd;
```

* right hand side is reference ( leeftijd )
* Left hand side is declaration (var a)

* console.log() = left hand side (Vraag console met de functie log aan en de waarde in de functie)
* console.log(leeftijd) = Haal de waarde van leeftijd op om het mee tegeven aan de left hand side

* a = 23; a en 23 Left hand side omdat het geen waarde heeft maar een harde value heeft
* a = leeftijd; a is left hand omdat het een waarde moet worden, scope a moet een waarde krijgen. Leeftijd is right hand side omdat de waarde van leeftijd moet worden opgehaald.
* b = a; b is left hand en a is right hand. De waarde van a moet weer worden opgehaald.

```javascript
function foo(a) {
  console.log(a);
}

foo(2);
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

**Onderstaande content is uit het boek [YDKJS](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch1.md);**

## Review (TL;DR)

Scope is the set of rules that determines where and how a variable (identifier) can be looked-up. This look-up may be for the purposes of assigning to the variable, which is an LHS (left-hand-side) reference, or it may be for the purposes of retrieving its value, which is an RHS (right-hand-side) reference.

LHS references result from assignment operations. Scope-related assignments can occur either with the = operator or by passing arguments to (assign to) function parameters.

The JavaScript Engine first compiles code before it executes, and in so doing, it splits up statements like var a = 2; into two separate steps:

* First, var a to declare it in that Scope. This is performed at the beginning, before code execution.
* Later, a = 2 to look up the variable (LHS reference) and assign to it if found.

Both LHS and RHS reference look-ups start at the currently executing Scope, and if need be (that is, they don't find what they're looking for there), they work their way up the nested Scope, one scope (floor) at a time, looking for the identifier, until they get to the global (top floor) and stop, and either find it, or don't.

Unfulfilled RHS references result in ReferenceErrors being thrown. Unfulfilled LHS references result in an automatic, implicitly-created global of that name (if not in "Strict Mode" [^note-strictmode]), or a ReferenceError (if in "Strict Mode" [^note-strictmode]).

**Quiz Answers**

```javascript
function foo(a) {
  var b = a;
  return a + b;
}
```

var c = foo( 2 );
Identify all the LHS look-ups (there are 3!).

c = .., a = 2 (implicit param assignment) and b = ..

Identify all the RHS look-ups (there are 4!).

foo(2.., = a;, a + .. and .. + b
