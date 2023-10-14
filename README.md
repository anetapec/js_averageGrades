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
```bash


function test() {
     const sentence = "To jest przykladowe zdanie."
     console.log(sentence);
     let fragment1 = sentence.slice(2,10); // frgm zdania od 3 do 11
     console.log(fragment1);
     let fragment2 = sentence.substring(11,18); // frgm zdania od 12 do 19 
     console.log(fragment2);
     let fragment3 = sentence.substr(20,6); //  fragment zdania zaczynający się od 21 znaku i mający długość 6 znaków  
     console.log(fragment2);
     
}

test();
```
# test czy masz wystarczający wzrost
```bash
function test() {
    // Miejsce na kod JS
    const MINIMALNY_WZROST = 150;
 
    let wzrost = prompt("Podaj swoj wzrost w centymetrach:");
 
    if (isNaN(wzrost)) {
        alert("Podaj poprawna wartosc liczbowa!");
    } else {
        if (wzrost >= MINIMALNY_WZROST) {
            alert("Mozesz skorzystac z karuzeli!");
        } else {
            alert("Jestes za niski, zeby skorzystac z karuzeli.");
        }
    }
}
 
test();
// <button onclick="test()">Kalkulator wzrostu</button> => HTML
```
# if-else BOOLEAN
```bash
function test() {
    // Miejsce na kod JS
    const czyChceszPizze = true;
 
    if (czyChceszPizze) {
        console.log("Super, jedziemy po pizze!");
    } else {
        console.log("Okej, może nastepnym razem.");
    }
}
 
test();
```
# warunek ? wartość_jeśli_prawda : wartość_jeśli_fałsz - operator warunkowy trójargumentowy ?
```bash
function test() {
 
    let age = 14;
 
    let status = age >= 18 ? true : false;
 
    if (status) {
        console.log("Jestes pelnoletni!");
    } else {
        console.log("Nie jestes jeszcze pelnoletni.");
    }
}
 
test();
```
# .prompt(), parseInt(), operatory logiczne
```bash
function test() {
   let year = parseInt(prompt("Wpisz rok "));
   let isLeapYear = (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
   if (year >= 2001 && year <= 2100 && isLeapYear) {
       alert(`${year} jest przestepny i nalezy do XXI wieku.`);
    } else if (year >= 2001 && year <= 2100 && !isLeapYear) {
        alert(`${year} nie jest przestepny i nalezy do XXI wieku.`);
    } else {
        alert(`${year} nie nalezy do XXI wieku.`);
   }
   

}

test();
```
## Operator koalescencji 
```bash
function test() {
    
    let price = 3200;
    let isRegularCustomer = true;
    let numberOfPurchases = 3;
    let discount = isRegularCustomer
        ? (numberOfPurchases ?? 0) >= 3
            ? 10
            : 0
        : 0;
    let totalPrice = price - (price * discount) / 100;
 
    console.log(`Cena roweru: ${totalPrice} pln`);
}
 
test();
```
# kalkulator kalorii , while 
```bash
function test() {
    
 
    let sumaKalorii = 0;
    let wprowadzoneKalorie;
 
    while (wprowadzoneKalorie !== "stop") {
        wprowadzoneKalorie = prompt(
            "Podaj kalorycznosc kolejnego posilku (lub wpisz 'stop' by zakonczyc):"
        );
        if (wprowadzoneKalorie !== "stop") {
            sumaKalorii += parseInt(wprowadzoneKalorie);
        }
    }
 
    alert(`laczna liczba spozytych kalorii: ${sumaKalorii}`);
}
 
test();
```
# zgadnij liczbę ,while
```bash

            const szukanaLiczba = Math.floor(Math.random() * 10) + 1;
             
            alert("Witaj w loterii! Zgadnij liczbe od 1 do 10. Masz 5 prob.");
             
            let liczbaProb = 5;
             
            while (liczbaProb > 0) {
                const zgadywanaLiczba = parseInt(prompt("Podaj liczbe:"));
             
                if (zgadywanaLiczba == szukanaLiczba) {
                    alert("Gratulacje! Zgadles(as)!");
                    break;
                } else if (zgadywanaLiczba < szukanaLiczba) {
                    alert("Podana liczba jest za mala. Sprobuj ponownie.");
                } else {
                    alert("Podana liczba jest za duza. Sprobuj ponownie.");
                }
             
                liczbaProb--;
            }
             
            if (liczbaProb === 0) {
                alert("Przegrales(as)! Szukana liczba to: " + szukanaLiczba);
            }
```
# kalkulator cen - do while;
```bash

function test() {
    let suma = 0;
    let cena;
    do {
         cena = parseFloat(prompt("Podaj cene: (wpisz 0, by zakończyć"));
        suma += cena;
    } while (cena !== 0);
    alert("Łączna wartość produktów wynosi:" + suma.toFixed(2));
    
    
    
}


test();
```
# pepier kamień nożyce
```bash
 const opcje = ["kamien", "papier", "nozyce"];
 
    alert(
        'Witaj w grze Kamien, Papier, Nozyce! Rozpocznij gre lub wpisz "q", aby zakonczyc.'
    );
 
    do {
        const wyborUzytkownika = prompt(
            'Wybierz: kamien, papier, nozyce (lub "q" aby zakonczyc):'
        );
 
        if (wyborUzytkownika === "q") {
            alert("Dziekujemy za gre. Do widzenia!");
            break;
        }
 
        const losowyIndeks = Math.floor(Math.random() * opcje.length);
        const wyborKomputera = opcje[losowyIndeks];
 
        if (wyborUzytkownika === wyborKomputera) {
            alert("Remis! Wybraliscie obie strony " + wyborUzytkownika + ".");
        } else if (
            (wyborUzytkownika === "kamien" && wyborKomputera === "nozyce") ||
            (wyborUzytkownika === "papier" && wyborKomputera === "kamien") ||
            (wyborUzytkownika === "nozyce" && wyborKomputera === "papier")
        ) {
            alert(
                "Gratulacje! Wygrales! Twoj " +
                    wyborUzytkownika +
                    " pokonuje " +
                    wyborKomputera +
                    "."
            );
        } else {
            alert(
                "Przegrales! Twoj " +
                    wyborUzytkownika +
                    " jest pokonany przez " +
                    wyborKomputera +
                    "."
            );
        }
    } while (true);
```
# zlczenie ile liter ma kazde słowo w zdaniu - pętla for 
```bash
function policzDlugoscSlowa(zdanie) {
    const slowa = zdanie.split(" ");
    const dlugosci = [];
 
    for (let i = 0; i < slowa.length; i++) {
        const dlugosc = slowa[i].length;
        dlugosci.push(dlugosc);
    }
 
    return dlugosci;
}
 
const zdanie = "To jest przykladowe zdanie do analizy";
const dlugosciSlow = policzDlugoscSlowa(zdanie);
 
console.log("Dlugosci slow w zdaniu:", dlugosciSlow);
```
# wyliczenie średniej temperatury , pętla for
```bash
function test() {
    
    const temperatures = [25, 30, 28, 22, 27];
    let sum = 0;
 
    for (let i = 0; i < temperatures.length; i++) {
        sum += temperatures[i];
    }
 
    const average = sum / temperatures.length;
    console.log("Srednia temperatura wynosi: " + average);
}
 
test();
```
# znajdz perwszą liczę pierwszą w tablicy liczb 
```bash
function test() {
    // Miejsce na kod JS
    const numbers = [10, 7, 4, 12, 11, 20, 9, 13];
 
    function isPrime(number) {
        if (number < 2) {
            return false;
        }
 
        for (let i = 2; i < number; i++) {
            if (number % i === 0) {
                return false;
            }
        }
 
        return true;
    }
 
    for (let i = 0; i < numbers.length; i++) {
        if (isPrime(numbers[i])) {
            console.log("Pierwsza liczba znaleziona: " + numbers[i]);
            break;
        }
    }
}
 
test();
```
# obliczenie średniej ocen 
```bash
function test() {
    // Miejsce na kod JS
    const grades = [3, 4, 5, 2, 3, 5, 4, 2, 4, 5];
    let sum = 0;
    let count = 0;
 
    for (let i = 0; i < grades.length; i++) {
        if (grades[i] < 3) {
            continue;
        }
 
        sum += grades[i];
        count++;
    }
 
    const average = sum / count;
    console.log(
        "Srednia ocen (bez ocen niedostatecznych): " + average.toFixed(2)
    );
}
 
test();
```
# obliczenie kosztu wysyłki w żależności od formy dostawy - switch
```bash
function test() {
    // Miejsce na kod JS
    const deliveryMethod = "kurier";
    let cost = 0;
 
    switch (deliveryMethod) {
        case "kurier":
            cost = 15;
            break;
        case "poczta":
            cost = 10;
            break;
        case "odbior osobisty":
            cost = 0;
            break;
        default:
            console.log("Nieznana metoda dostawy.");
    }
 
    console.log("Koszt wysylki: " + cost + " pln");
}
 
test();
```
















