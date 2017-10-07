---
title: "Перегрузка операторов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- operator_cpp
- operator
dev_langs:
- C++
helpviewer_keywords:
- redefinable operators [C++]
- non-redefinable operators [C++]
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5ac9415ec186760a70394772ffaff011d7c68c95
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="operator-overloading"></a>Перегрузка операторов
Ключевое слово `operator` объявляет функцию, которая указывает, что означает `operator-symbol` при применении к экземпляру класса. Это дает оператору более одного значения — "перегружает" его. Компилятор различает разные значения оператора, проверяя типы его операндов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## <a name="remarks"></a>Примечания  
 Функцию большинства встроенных операторов можно переопределить глобально или для отдельных классов. Перегруженные операторы реализуются в виде функции.  
  
 Имя перегруженного оператора `operator x`, где `x` является оператором, как оно указано в следующей таблице. Например, для перегрузки оператора сложения необходимо определить функцию `operator+`. Аналогично, для сложения/присвоения `+=` необходимо определить функцию `operator+=`.  
  
### <a name="redefinable-operators"></a>Переопределяемые операторы  
  
|Оператор|Имя|Тип|  
|--------------|----------|----------|  
|`,`|Comma|Binary|  
|`!`|Логическое НЕ|Унарный|  
|`!=`|Неравенство|Binary|  
|`%`|Модуль|Binary|  
|`%=`|Назначение модуля|Binary|  
|`&`|Побитовое И|Binary|  
|`&`|Взятие адреса|Унарный|  
|`&&`|Логическое И|Binary|  
|`&=`|Назначение побитового И|Binary|  
|`( )`|Вызов функции |—|  
|`( )`|Оператор приведения типа|Унарный|  
|`*`|Умножение|Binary|  
|`*`|Разыменование указателя|Унарный|  
|`*=`|Присваивание умножения|Binary|  
|`+`|Сложение|Binary|  
|`+`|Унарный плюс|Унарный|  
|`++`|Приращение <sup>1</sup>|Унарный|  
|`+=`|Присваивание сложения|Binary|  
|`-`|Вычитание|Binary|  
|`-`|Унарное отрицание|Унарный|  
|`--`|Уменьшение <sup>1</sup>|Унарный|  
|`-=`|Присваивание вычитания|Binary|  
|`->`|Выбор члена|Binary|  
|`->*`|Выбор указателя на член|Binary|  
|`/`|Деление|Binary|  
|`/=`|Присваивание деления|Binary|  
|`<`|Меньше|Binary|  
|`<<`|Сдвиг влево|Binary|  
|`<<=`|Сдвиг влево и присваивание|Binary|  
|`<=`|Меньше или равно|Binary|  
|`=`|Присваивание|Binary|  
|`==`|Равенство|Binary|  
|`>`|Больше|Binary|  
|`>=`|Больше или равно|Binary|  
|`>>`|Сдвиг вправо|Binary|  
|`>>=`|Сдвиг вправо и присваивание|Binary|  
|`[ ]`|Нижний индекс массива|—|  
|`^`|Исключающее ИЛИ|Binary|  
|`^=`|Исключающее ИЛИ/присваивание|Binary|  
|`&#124;`|Побитовое включающее ИЛИ|Binary|  
|`&#124;=`|Назначение побитового включающего ИЛИ|Binary|  
|`&#124;&#124;`|Логическое ИЛИ|Binary|  
|`~`|Дополнение до единицы|Унарный|  
|`delete`|`Delete`|—|  
|`new`|`New`|—|  
|`conversion operators`|операторы преобразования|Унарный|  
  
 1 две версии унарных инкремента и декремента существует: префиксная и постфиксная.  
  
 В разделе [общие правила перегрузки операторов](../cpp/general-rules-for-operator-overloading.md) для получения дополнительной информации. Ограничения для разных категорий перегруженных операторов описываются в следующих разделах.  
  
-   [Унарные операторы](../cpp/overloading-unary-operators.md)  
  
-   [Бинарные операторы](../cpp/binary-operators.md)  
  
-   [Назначение](../cpp/assignment.md)  
  
-   [Вызов функции](../cpp/function-call-cpp.md)  
  
-   [Индексация](../cpp/subscripting.md)  
  
-   [Доступ к членам класса](../cpp/member-access.md)  
  
-   [Увеличение и уменьшение](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
-   [Заданные пользователем преобразования типов](../cpp/user-defined-type-conversions-cpp.md)  
  
 Операторы, перечисленные в следующей таблице, не могут быть перегружены. В этой таблице содержатся символы препроцессора `#` и `##`.  
  
### <a name="nonredefinable-operators"></a>Непереопределяемые операторы  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|Выбор члена|  
|`.*`|Выбор указателя на член|  
|`::`|Разрешение области|  
|`? :`|Условие|  
|`#`|Препроцессор: преобразование в строку|  
|`##`|Препроцессор: конкатенация|  
  
 Хотя перегруженные операторы обычно называются компилятором неявным образом при их появлении в коде, их можно вызывать и явным образом — точно так же, как и любую функцию-член или функцию, не являющуюся членом.  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется перегрузка оператора `+`, после чего он складывает два комплексных числа и возвращает результат.  
  
```  
// operator_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Complex {  
   Complex( double r, double i ) : re(r), im(i) {}  
   Complex operator+( Complex &other );  
   void Display( ) {   cout << re << ", " << im << endl; }  
private:  
   double re, im;  
};  
  
// Operator overloaded using a member function  
Complex Complex::operator+( Complex &other ) {  
   return Complex( re + other.re, im + other.im );  
}  
  
int main() {  
   Complex a = Complex( 1.2, 3.4 );  
   Complex b = Complex( 5.6, 7.8 );  
   Complex c = Complex( 0.0, 0.0 );  
  
   c = a + b;  
   c.Display();  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
6.8, 11.2  
```  
  
## <a name="in-this-section"></a>Содержание раздела  
  
1.  [Общие правила перегрузки операторов](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [Перегрузка унарных операторов](../cpp/overloading-unary-operators.md)  
  
3.  [Бинарные операторы](../cpp/binary-operators.md)  
  
4.  [Назначение](../cpp/assignment.md)  
  
5.  [Вызов функции](../cpp/function-call-cpp.md)  
  
6.  [Индексация](../cpp/subscripting.md)  
  
7.  [Доступ к членам](../cpp/member-access.md)  
  
## <a name="see-also"></a>См. также  
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
