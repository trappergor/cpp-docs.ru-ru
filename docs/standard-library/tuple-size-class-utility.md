---
title: "Класс tuple_size &lt;utility&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tuple_size"
  - "std::tr1::tuple_size"
  - "std.tr1.tuple_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс tuple_size <utility> (TR1)"
ms.assetid: 36d04207-ed87-4c11-9875-150c59833b79
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс tuple_size &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает оболочку для счетчика элементов `pair`.  
  
## Синтаксис  
  
```  
template<class Tuple>  
struct tuple_size;  
  
template<class T1, class T2>  
struct tuple_size<pair<T1, T2>>   : integral_constant<size_t, 2>  
  
// size of const tuple  
template<class Tuple>  
struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template<class Tuple>  
struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template<class Tuple>  
struct tuple_size<const volatile Tuple>;  
```  
  
#### Параметры  
 `T1`  
 Тип первого элемента пары.  
  
 `T2`  
 Тип второго элемента пары.  
  
## Заметки  
 Шаблон является специализацией класса шаблона [Класс tuple\_size](../standard-library/tuple-size-class-tuple.md). У него есть член `value`, который представляет собой интегральное константное выражение со значением 2.  
  
## Пример  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
  
int main()  
{  
    MyPair c0(0, 1.1);  
  
    // display contents " 0 1.1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display size " 2"   
    cout << " " << tuple_size<MyPair>::value << endl;  
  
}  
  
/*  
Output:  
0 1.1  
2  
*/  
```  
  
## Требования  
 **Заголовок:** \<utility\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<utility\>](../standard-library/utility.md)   
 [Функция get](../Topic/get%20Function%20%3Cutility%3E.md)   
 [Класс tuple\_element](../standard-library/tuple-element-class-utility.md)