---
title: "Предупреждение компилятора (уровень 4) C4437 | Microsoft Docs"
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
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Предупреждение компилятора (уровень 4) C4437
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dynamic\_cast из базы «class1» " в «класс» может завершиться ошибкой в определенных контекстах будет компилироваться с \/vd2 или определяет «класс» с vtordisp \#pragma \(2\) в результате  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
 Компилятором обнаружена операция `dynamic_cast` со следующими характеристиками.  
  
-   Приведение указателя базового класса в указатель производного класса.  
  
-   Производный класс наследует виртуального базового класса.  
  
-   Производный класс не имеет поле `vtordisp` для виртуальной базы данных.  
  
-   Приведение не найдено в конструкторе или деструкторе производного класса, или несколько класса, значительно наследуется от производного класса \(в противном случае будет выдано предупреждение компилятора C4436\).  
  
 Предупреждение означает, что `dynamic_cast` может не работать правильно, если он работает частично встраивается в объекте.  Такая ситуация возникает при открытии функция вызывается из конструктора или деструктора класса, который наследует с именем производного класса в предупреждении.  Если с именем производного класса в предупреждении никогда дальнеиший производно или внешней функции не вызывается во время создания или удаления объекта, предупреждение можно игнорировать.  
  
## Пример  
 Следующий пример приводит C4437 проблему и демонстрация создания кода, которая исходит от отсутствующего поля `vtordisp`.  
  
```cpp  
// C4437.cpp  
// To see the warning and runtime assert, compile with: /W4  
// To eliminate the warning and assert, compile with: /W4 /vd2  
//       or compile with: /W4 /DFIX  
#pragma warning(default : 4437)  
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
        func();  
    }  
  
    void func()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4437  
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
 [Предупреждение компилятора \(уровень 1\) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)