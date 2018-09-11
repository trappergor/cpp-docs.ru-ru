---
title: Оператор if-else (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- else_cpp
- if_cpp
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4aea3a0125e2712203eb668197d42bd850aef5e
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131895"
---
# <a name="if-else-statement-c"></a>Оператор if-else (C++)
Управляет условным ветвлением. Инструкции в *блок if* выполняются только в том случае, если *выражение if* принимает значение, отличное от нуля значение (или TRUE). Если значение *выражение* не равно нулю, *оператор1* -блок else, если он присутствует, пропускается и выполнения любых операторов в блоке. Если значение *выражение* равно нулю, а затем блоке if пропускается, а также-блок else, если он присутствует, при выполнении. Выражения, которые возвращают ненулевое значение —
- true
- указатель не null
- арифметические любое ненулевое значение, или 
- Введите тип класса, который определяет однозначное преобразование в арифметический тип, логическое значение или указатель. (Сведения о преобразованиях см. в разделе [стандартные преобразования](../cpp/standard-conversions.md).)   
  
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

```cpp  
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
## <a name="if_with_init"></a> Если инструкция, с помощью инициализатора

**Visual Studio 2017 версии 15.3 и более поздние версии** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): **Если** инструкция также может содержать выражение, которое объявляет и инициализирует именованной переменной. Используйте эту форму инструкции if, когда нужна только в пределах блока if. 

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

 В все виды **Если** инструкции *выражение*, вычисляется которого может иметь любое значение, за исключением структуры, включая все побочные эффекты. Управление передается из **Если** оператора к следующему оператору в программе Если один из *инструкции*s содержит [break](../cpp/break-statement-cpp.md), [по-прежнему](../cpp/continue-statement-cpp.md), или [goto](../cpp/goto-statement-cpp.md).  
  
 **Else** предложении `if...else` оператор связан с ближайшим предыдущих **Если** инструкции в той же области, который не имеет соответствующего **else** инструкция.   

## <a name="a-nameifconstexpr-if-constexpr-statements"></a><a name="if_constexpr"> Если инструкции constexpr
**Visual Studio 2017 версии 15.3 и более поздние версии** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): В шаблонах функций, можно использовать **Если constexpr** инструкцию, чтобы принимать решения ветвления во время компиляции без приходится прибегать к несколько перегрузок функций. Например можно написать одну функцию параметра, дескрипторы, распаковки, (ни одной перегрузке не нулевой параметр является обязательным): 

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
// handle t
   do_something(t);

   // handle r conditionally
   if constexpr (sizeof...(r)) 
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