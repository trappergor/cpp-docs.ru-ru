---
title: "Вызов (C++) функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e066ab4c154c04c0c1a39b7f8d0164881a0a96cc
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
