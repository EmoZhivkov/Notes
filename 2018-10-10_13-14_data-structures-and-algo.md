---
tags:
  - data-structures-and-algo
---

# Свойства на сортировките - bubble sort, insertion sort, selection sort
- stable sort, in place vs outplace (не използва никаква допълнителна памет),
time complexity, space complexity, number of comparisons, adaptivity (ако му дадем инсършън сорт, мн по-бързо ще ги сортира, входните данни дали ако имат някакво свойство, дали ще се промени бързината), Online (когато не се нуждае целия вход да му се подаде, примерно можем да подаваме един по един и винаги ще ги държи сортирани)

## - Може ли да се дефинира сортировка само ако знаем дали един елемент е по-малък от друг
    - не защото, ако А < Б, Б < С, С < А - това се чупи
    - за да може трябва следните неща да са вярни:
        - А <= Б и Б <= А, to A = Б (антисиметричност)
        - А <= Б и Б <= С, то А <= С (транзитивност)
        - всеки А <= А (рефлексивност)

## Bubble sort
- метод на мехурчето - (1), (2), (4), (2), (5), да си представим, че тази редица е наредена вертикално,
нека тежестта да е това колко въздух има

(1)     (5)
(2)     (4)
(4) =>  (2)
(2)     (2)
(5)     (1)

(най-простия вариант)
void bubbleSort(int* array, int lenght) {
    for(int i = 0: i < lenght; i++) {

        bool flag = false;
        for(int c = 0; c < lenght- i -1; c++) { (dobawq se edno (- i))

            if (array[c] > array[c + 1]) {
                swap(array[c], array[c + 1]);

                flag = true;
            }

        }
        if (!flag) break;
    }
}

- time complexity - O(lenght^2)
- space complexity - O(1)
- stable: true
- number of comparisons - O(lenght^2)
- number of swaps - O(lenght^2)
- online: false
- in place - true
- adaptive - yes


## Selection sort

void selectionSort(int *array, int p) {
    for (int i = 0; i < p; i++) {
        int idx = i;
        for (int c = i + 1; c < p; c++) {
            if (array[c] < array[idx]) {
                idx = c;
            }
        }
        swap(array[i], array[idx]);
    }
}

- time complex - O(p^2)
- space complex - O(1)
- stable - true
- number of comparisons - O(p^2)
- number of swaps - O(p)
- online - false
- in-place - true
- adaptive - false

## za kontrolnoto
- Обръщане на масив
- Всички сортировки
- всички сложности
- задачи свързани със сложност
- всеки елемент го повдига на трета на степен на масив ест
- функция, която приема стринг и връща обърнатия го обръща
- ф-ция, която проверява дали един стринг е палиндром


