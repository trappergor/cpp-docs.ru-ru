---
title: "Предупреждение компилятора (уровень 1) C4436 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# Предупреждение компилятора (уровень 1) C4436
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dynamic\_cast из базы «class1» " в «класс» в конструкторе или деструкторе может завершиться ошибкой с частично построение объектом компилировать с параметром \/vd2 или определяет «класс» с vtordisp \#pragma \(2\) в результате  
  
 Компилятором обнаружена операция `dynamic_cast` со следующими характеристиками.  
  
-   Приведение указателя базового класса в указатель производного класса.  
  
-   Производный класс наследует виртуального базового класса.  
  
-   Производный класс не имеет поле `vtordisp` для виртуальной базы данных.  
  
-   Приведение найдено в конструкторе или деструкторе производного класса, или несколько класса, значительно наследуется из производного класса.  
  
 Предупреждение означает, что `dynamic_cast` может не работать правильно, если он работает частично встраивается в объекте.  Это происходит, если производные конструктор и деструктор работают на часть объекта какого\-либо более добавочного производного объекта.  Если производный класс в предупреждении никогда дальнеиший получен, предупреждение можно игнорировать.  
  
## Пример  
 Следующий пример приводит C4436 проблему и демонстрация создания кода, которая исходит от отсутствующего поля `vtordisp`.  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## См. также  
 [Оператор dynamic\_cast](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../Topic/vtordisp.md)   
 [Предупреждение компилятора \(уровень 4\) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)