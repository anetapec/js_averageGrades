# js_averageGrades
```bash

 
function test() {
    const students = [
        {
            name: "Jan",
            surname: "Kowalski",
            age: 21,
            index: "12345",
            grades: [4, 5, 3, 2],
        },
        {
            name: "Anna",
            surname: "Nowak",
            age: 22,
            index: "23456",
            grades: [5, 5, 5, 4],
        },
        {
            name: "Piotr",
            surname: "Wisniewski",
            age: 20,
            index: "34567",
            grades: [3, 3, 2, 2],
        },
    ];
 
    function calculateAverageGrade(students) {
        let averageGrades = {};
 
        for (let student of students) {
            let studentGrades = student.grades;
            let average =
                studentGrades.reduce((a, b) => a + b) / studentGrades.length;
            averageGrades[student.surname] = average;
        }
 
        let overallAverage =
            Object.values(averageGrades).reduce((a, b) => a + b) /
            students.length;
 
        console.log(
            `Średnia ocen dla każdego studenta (${Object.keys(
                averageGrades
            )}): ${averageGrades["Kowalski"]}, ${averageGrades["Nowak"]}, ${
                averageGrades["Wisniewski"]
            }`
        );
        console.log(`Ogólna średnia ocen: ${overallAverage.toFixed(2)}`);
    }
 
    calculateAverageGrade(students);
}
 
test();
```
## alert, prompt
```bash
"use strict";

// Miejsce na kod JS
function greetUser() {
  const name = prompt("Jak masz na imie?");


if (name) {
    alert(`Witaj ${name}! Milo Cie poznac.`);
} else {
    alert("Nie podales swojego imienia. Sprobuj jeszcze raz.");
}
}

//  <button onclick="greetUser()">Kliknij, aby się przywitać</button>   =>HTML
```
# confirm => zapytanie o pewność decyzji
```bash
function askConfirmation() {
  const decisionConfirmed = confirm("Czy na pewno chcesz wykonać zakończyć?");
  
    if (decisionConfirmed) {
        alert("Twoja decyzja została potwierdzona.");
    } else {
        alert("Twoja decyzja została anulowana.");
    }
}
//  <button onclick="askConfirmation()">Kliknij, aby zadać pytanie</button> => HTML
```
# Bolean i Number
```bash function test() {
    let koszt = "25.50";
    
    let kosztLiczba =  Number(koszt);
    let kosztAkcept = Boolean (kosztLiczba > 20);
    
    if (kosztAkcept) {
        console.log("Zamowienie zaakceptowane");
    } else {
        console.log("Koszt zamowienia musi byc wiekszy niz 20 zl");
    }
}
    


test();
```
## 
Inkrementacja / Dekrementacja => zwiększ/zmniejsz licznik

```bash
let licznik = 0;
function zwiekszLicznik() {
    licznik ++
    aktualizujWynik();
}
function zmniejszLicznik() {
  licznik--;
  aktualizujWynik();
}
function aktualizujWynik() {
  document.getElementById("wynik").textContent = licznik;
}

aktualizujWynik();

//    <button onclick="zwiekszLicznik()">Zwiększ licznik</button>
// <button onclick="zmniejszLicznik()">Zmniejsz licznik</button>
// <div id="wynik">0</div>
```
# sprawdzenie czy uzytkownik spełnia warunki by prowadzić pojazd
```bash


function test() {
    const minAge = 18;
    
    const age = parseInt(prompt("Podaj swoj wiek:"));
    const hasLicense = prompt("Czy posiadasz prawo jazdy? (Tak/Nie)");
    
    if (age >= minAge && hasLicense.toLowerCase() === "tak") {
        alert("Mozesz wypozyczyc samochod!");
    } else {
        alert("Nie mozesz wypozyczyc samochodu. Brak wymaganych dokumentow / niepelnoletni.")
    }
    

}

test();
```
# porównanie
```bash


function test() {
    let name = null;
    let surname;
    
    console.log(name == surname);
    console.log(name === surname);
}
    
    
test();
```
# podatek Vat
```bash


function test() {
    let basePrice = 50;
    let vatRate = 0.23;
    
    let vatAmount = basePrice * vatRate;
    
    let totalPrice = basePrice + vatAmount;
    
    console.log("Bazowa cena:", basePrice);

    console.log("Podatek VAT:", vatAmount);

    console.log("Całkowita cena:", totalPrice);
    
     
}

test();
```
## Math.floor(), Math.ceil(), Math.round() 
```bash
function test() {
    let number = 3.7;
    let floorResult = Math.floor(number); // do najbliższej liczby całkowitej w DÓŁ
    let ceilResult = Math.ceil(number);  //  do najbliższej liczby całkowitej w GÓRĘ
    let roundResult = Math.round(number); // do najbliższej liczby całkowitej
}
test()
```
## isNaN / isFinite
```bash
function test() {
    function validateNumber(number) {
        if (isNaN(number)) {
            console.log("Podana wartosc nie jest liczba.");
        } else if (!isFinite(number)) {
            console.log("Podana liczba jest nieskonczona.");
        } else {
            console.log("Podana wartosc jest prawidlowa liczba.");
        }
    }
 
    validateNumber(10); // Prawidlowa liczba
    validateNumber("ABC"); // Nie jest liczba
    validateNumber(Infinity); // Nieskonczonosc
}
 
test();
```
# OPERACJE NA STRINGACH  
##  str - wyświetlenie długości zdania, pierwszej i ostatniej litery, sprawdzenie, czy zdanie zawiera określone słowo..- .includes !!!
```bash



function test() {
     const sentence = "To jest przykladowe zdanie.";
     console.log(`Dlugosc zdania: ${sentence.length}`);
     console.log(`Pierwsza litera zdania: ${sentence[0]}`);
     console.log(`Ostatnia litera zdania: ${sentence[sentence.length - 1]}`);
     
     const wordToCheck = "przykladowe";
     // .includes !!!
    console.log(`Czy zdanie zawiera slowo "${wordToCheck}"? ${sentence.includes(wordToCheck)}`);

    // zmiana pierwszej litery zdania na małą 
    
    const modifiedSentence = sentence[0].toLowerCase() + sentence.slice(1);
    console.log(`Zmodyfikowane zdanie: ${modifiedSentence}`);
    // .slice => WYCINAMY FRGM TEKSTU OD DANEGO MIEJSCA

}

test();
```
## String - metody slice / substring / substr


















