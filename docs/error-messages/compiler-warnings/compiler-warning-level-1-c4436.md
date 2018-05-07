---
title: Предупреждение (уровень 1) C4436 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1da06a329a9c0bdfcff6877ce69c8e3672619bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4436"></a>Предупреждение компилятора (уровень 1) C4436
приведение dynamic_cast из виртуального базового типа «class1» в «class2» в конструктор или деструктор может завершаться с частично сконструированного объекта компиляции с параметром/vd2 или определите «класс2» с #pragma vtordisp(2) фактически  
  
 Компилятор обнаружил `dynamic_cast` операции со следующими характеристиками.  
  
-   Из указателя базового класса является приведение указателя на производный класс.  
  
-   Производный класс наследует практически базового класса.  
  
-   Производный класс не имеет `vtordisp` для виртуального базового.  
  
-   Приведение встречается в конструктор или деструктор производного класса, или некоторые дополнительные класс наследует от производного класса.  
  
 Предупреждение указывает `dynamic_cast` может неправильно работать правильно, если он работает на частично сконструированного объекта.  Что происходит, если производного конструктора или деструктора работает на дочерний объект либо последующего производного объекта.  Если производный класс в предупреждении никогда не дальнейших производным, это предупреждение можно пропустить.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4436 и демонстрирует проблему создания кода, возникают из-за отсутствующего `vtordisp` поля.  
  
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
  
## <a name="see-also"></a>См. также  
 [Оператор dynamic_cast](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [Предупреждение компилятора (уровень 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)