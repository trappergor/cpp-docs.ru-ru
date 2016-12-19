---
title: "Индексация | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], индексация"
  - "перегрузка операторов, примеры"
  - "операторы [C++], перегрузка"
  - "подстрочный оператор"
  - "подстрочный оператор, перегруженные"
  - "индексация"
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Индексация
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор индекса \(**\[ \]**\), как и оператор вызова функции, считается бинарным оператором.  Оператор индекса должен быть нестатической функцией\-членом, которая принимает один аргумент.  Этот аргумент может быть любого типа и определяет требуемый индекс массива.  
  
## Пример  
 В следующем примере показано, как создать вектор типа `int`, в котором реализована проверка границ:  
  
```  
// subscripting.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class IntVector {  
public:  
   IntVector( int cElements );  
   ~IntVector() { delete [] _iElements; }  
   int& operator[](int nSubscript);  
private:  
   int *_iElements;  
   int _iUpperBound;  
};  
  
// Construct an IntVector.  
IntVector::IntVector( int cElements ) {  
   _iElements = new int[cElements];  
   _iUpperBound = cElements;  
}  
  
// Subscript operator for IntVector.  
int& IntVector::operator[](int nSubscript) {  
   static int iErr = -1;  
  
   if( nSubscript >= 0 && nSubscript < _iUpperBound )  
      return _iElements[nSubscript];  
   else {  
      clog << "Array bounds violation." << endl;  
      return iErr;  
   }  
}  
  
// Test the IntVector class.  
int main() {  
   IntVector v( 10 );  
   int i;  
  
   for( i = 0; i <= 10; ++i )  
      v[i] = i;  
  
   v[3] = v[9];  
  
   for ( i = 0; i <= 10; ++i )  
      cout << "Element: [" << i << "] = " << v[i] << endl;  
}  
```  
  
  **Нарушение границ массива.**  
**Элемент: \[0\] \= 0**  
**Элемент: \[1\] \= 1**  
**Элемент: \[2\] \= 2**  
**Элемент: \[3\] \= 9**  
**Элемент: \[4\] \= 4**  
**Элемент: \[5\] \= 5**  
**Элемент: \[6\] \= 6**  
**Элемент: \[7\] \= 7**  
**Элемент: \[8\] \= 8**  
**Элемент: \[9\] \= 9**  
**Нарушение границ массива.**  
**Элемент: \[10\] \= 10**   
## Комментарии  
 Когда в предыдущей программе для переменной `i` достигается значение 10, функция `operator[]` обнаруживает выход индекса за допустимые границы и выдает сообщение об ошибке.  
  
 Обратите внимание, что функция `operator[]` возвращает ссылочный тип.  В результате она является значением l\-value, что позволяет использовать выражения с индексами с любой стороны операторов присваивания.  
  
## См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)