# js_averageGrades
```bash
"use strict";
 
function test() {
    // Miejsce na kod JS
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
