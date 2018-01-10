---
title: "Вызов (C++) функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- function calls, C++ functions
- functions [C++], calling
- operator overloading [C++], function calls
- function overloading [C++], function-call operator
- function calls, operator
- operators [C++], overloading
- operator overloading [C++], examples
- function call operator ()
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6d130f087f635306083e58faf7c77b252fc9360
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="function-call-c"></a>Вызов функций (C++)
Оператор вызова функции, записываемый при помощи скобок, является бинарным оператором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
primary-expression ( expression-list )  
```  
  
## <a name="remarks"></a>Примечания  
 В этом контексте `primary-expression` является первым операндом, а `expression-list` (список аргументов, который может быть пустым) — вторым. Оператор вызова функции используется для операций, для которых необходимо определенное количество параметров. Такой подход действует, потому что `expression-list` представляет собой не отдельный операнд, а список. Оператор вызова функции должен представлять собой нестатическую функцию-член.  
  
 Перезагрузка оператора вызова функции не меняет способ вызова функций; она лишь изменяет способ интерпретации оператора при применении к объектам заданного типа класса. К примеру, приведенный ниже код в обычных условиях не имеет смысла.  
  
```  
Point pt;  
pt( 3, 2 );  
```  
  
 Однако, если оператор вызова функции был соответствующим образом перегружен, то этот синтаксис может использоваться для сдвига координаты `x` на три единицы, а координаты `y` — на две. Такое определение приводится в следующем примере.  
  
```  
// function_call.cpp  
class Point  
{  
public:  
    Point() { _x = _y = 0; }  
    Point &operator()( int dx, int dy )  
        { _x += dx; _y += dy; return *this; }  
private:  
    int _x, _y;  
};  
  
int main()  
{  
   Point pt;  
   pt( 3, 2 );  
}  
```  
  
 Обратите внимание, что оператор вызова функции применяется к имени объекта, а не к имени функции.  
  
 Перегрузку оператора вызова функции также можно выполнить, используя указатель на функцию (вместо самой функции).  
  
```cpp  
typedef void(*ptf)();  
void func()  
{  
}  
struct S  
{  
   operator ptf()  
   {  
      return func;  
   }  
};  
  
int main()  
{  
   S s;  
   s();//operates as s.operator ptf()()  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)