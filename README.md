Вариант задания: Объявление и определение структуры на языке PHP:

struct Employee{
    string $firstName;
    string $lastName;
    int $salary;
    bool $fullTime;
};

Примеры допустимых строк: 

struct Person {
    string $name;
    int $age;
};

struct Product {
    string $title;
    double $price;
    bool $inStock;
};


Грамматика является автоматной.
1.	< START > → ‘STRUCT’ < SPACE >
2.	< SPACE > → ‘   ‘→ < Name >
3.	< Name > → ‘letter’ → < NameRem >
4.	< NameRem > → ‘letter’ → < NameRem >
5.	< NameRem >    → < Digit > < NameRem >
6.	< NameRem > → ‘{‘  < TYPE >
7.	< TYPE > → ‘string’ → < SPACE >
8.	< TYPE > → ‘int’ → < SPACE >
9.	< TYPE > → ‘bool’ → < SPACE >
10.	< TYPE > → ‘float’ → < SPACE >
11.	< TYPE > -> ‘double’ → < SPACE >
12.	< SPACE > → ‘   ‘→ < SPACE > 
13.	< SPACE > → ‘$’ → < StrRem >
14.	< StrRem > → symbol < StrRem >
15.	< StrRem > → ‘;’ < TYPE >
16.	< StrRem > → ‘;’ < END >
17.	< END>  → ‘}’ FINAL
18.	FINAL → ‘;’‹ E › → ‹ ; ›
    
•	‹ Digit › → “0” | “1” | “2” | “3” | “4” | “5” | “6” | “7” | “8” | “9”

•	‹ Letter › → “a” | “b” | “c” | ... | “z” | “A” | “B” | “C” | ... | “Z”

Следуя введенному формальному определению грамматики, представим G[‹Def›] ее составляющими:

Z = ‹ START ›;

VT = {a, b, c, ..., z, A, B, C, ..., Z, _,:, =, +, -, ;, ., 0, 1, 2, ..., 9};

VN ={‹ START ›,‹ SPACE ›,‹ Name ›,‹ NameRem ›, ‹ TYPE ›,‹ StrRem ›,‹ END ›,‹ FINAL ›,‹ Digit ›,‹ Letter ›}.


Правила (1) – (18) для G[‹Def›] реализованы на графе (см. рисунок 1).

Сплошные стрелки на графе характеризуют синтаксически верный разбор; пунктирные символизируют состояние ошибки (ERROR); 

Состояние 11 символизирует успешное завершение разбора.

Рисунок 1

![Граф](https://github.com/user-attachments/assets/21e53e90-ffef-43b0-bbea-e64e6712dc72)


Тестовые примеры:

![Рисунок3](https://github.com/user-attachments/assets/8ef6ce5d-17fd-4459-99fe-c6822a22bc36)

![Рисунок4](https://github.com/user-attachments/assets/7c3bcf00-2ab7-4749-b034-84707195636e)

