---
title: "Оператор if-else (C++) | Документы Microsoft"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- else_cpp
- else
- if_cpp
- if
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 7f6d2a553e34b5f15e53fa142241af83d8e91255
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="if-else-statement-c"></a>Оператор if-else (C++)
Управляет условным ветвлением. Операторы в *блок if* выполняются только в том случае, если *выражение if* имеет ненулевое значение (или `true`). Если значение *выражение* отлично от нуля, *Выражение1* -блок else, если он имеется, пропускается и выполнения любых операторов в блоке. Если значение *выражение* равно нулю, то блок if пропускается и -блок else, если он имеется, выполняется. Выражения, вычисляемые в ненулевое значение —
- `true`
- указатель, отличных от null
- любое ненулевое значение арифметические или 
- Введите тип класса, который определяет однозначное преобразование в арифметический тип, boolean или указатель. (Сведения о преобразованиях см. в разделе [стандартные преобразования](../cpp/standard-conversions.md).)   
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
if ( expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
} 

// Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
}  

// Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
} 
```  
## <a name="example"></a>Пример  
```  
// if_else_statement.cpp  
#include <iostream>

using namespace std;

class C
{
    public:
    void do_somthing(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

  // no else statement
    if (x == 10)
    {
        x = 0; 
    }
    
  
    C* c;
  init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```  
## <a name="if-statement-with-an-initializer"></a>Если инструкция с помощью инициализатора
**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): **Если** инструкция также может содержать выражение, которое объявляет и инициализирует переменную с именем. Используйте эту форму инструкции if при переменной требуется только в пределах блока if. 

```cpp
## Example  
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>


using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }


    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }

}
```

 В различное **Если** инструкции, *выражение*, который может иметь любое значение, за исключением структуры, оценки, включая все побочные эффекты. Управление передается из **Если** оператора к следующему оператору в программе пока один из *инструкции*s содержит [разрыв](../cpp/break-statement-cpp.md), [Продолжить](../cpp/continue-statement-cpp.md), или [goto](../cpp/goto-statement-cpp.md).  
  
 **Else** предложения `if...else` оператор связан с ближайшим предыдущих **Если** инструкции в той же области, у которого нет соответствующего **else** инструкция.   

## <a name="constexpr-if-statements"></a>constexpr Если инструкций
**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): В шаблонах функций, можно использовать **constexpr Если** инструкции для принятия решений ветвления во время компиляции не приходится прибегать к несколько перегрузок функции. Например можно написать одной функции, дескрипторы параметра при распаковке (не требуется ни одна перегрузка параметра нулевого): 

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
// handle t
   do_something(t);

   // handle r conditionally
   constexpr if (sizeof...(r)) 
   {
      
      f(r...); 
   }
   else
   {
       g(r...);
   }
}
```

  
 
## <a name="see-also"></a>См. также  
 [Операторы выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор switch (C++)](../cpp/switch-statement-cpp.md)
