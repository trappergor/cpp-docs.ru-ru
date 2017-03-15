---
title: "Оператор reinterpret_cast | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "reinterpret_cast"
  - "reinterpret_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reinterpret_cast - ключевое слово [C++]"
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Оператор reinterpret_cast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет преобразовывать любой указатель в указатель любого другого типа.  Также позволяет преобразовывать любой целочисленный тип в любой тип указателя и наоборот.  
  
## Синтаксис  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## Заметки  
 Неправильное использование оператора `reinterpret_cast` легко может оказаться небезопасным.  Если требуемое преобразование не является низкоуровневым по самой своей природе, следует использовать один из других операторов приведения типов.  
  
 Оператор `reinterpret_cast` можно использовать для таких преобразований, как `char*` в `int*` или `One_class*` в `Unrelated_class*`, которые небезопасны по самой своей сути.  
  
 Результат применения `reinterpret_cast` не может безопасно использоваться ни для чего другого, кроме приведения обратно в исходный тип.  Другие применения в лучшем случае будут непереносимыми.  
  
 Оператор `reinterpret_cast` не позволяет удалять атрибуты **const**, `volatile` и **\_\_unaligned**.  Дополнительные сведения об удалении этих атрибутов см. в разделе [Оператор const\_cast](../Topic/const_cast%20Operator.md).  
  
 Оператор `reinterpret_cast` преобразует значение пустого указателя в значение пустого указателя конечного типа.  
  
 Одним из практических применений оператора `reinterpret_cast` является хэш\-функция, которая сопоставляет значение индексу таким образом, что два несовпадающих значения редко соответствуют одинаковым индексам.  
  
```  
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 Оператор `reinterpret_cast` позволяет использовать указатель как целочисленный тип.  Затем для получения уникального индекса \(уникального с высокой степенью вероятности\) к результату применяется побитовый сдвиг и операция XOR с самим собой.  Далее индекс усекается с использованием стандартного для языка C приведения к типу возвращаемого значения функции.  
  
## См. также  
 [Операторы приведения](../cpp/casting-operators.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)