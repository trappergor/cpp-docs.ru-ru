---
title: "C4868 Предупреждение компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 26031e1ac6f39d745a772e1becf3f817213a59d8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4868"></a>C4868 Предупреждение компилятора
Компилятор «file(line_number)» не может принудительного порядка оценки слева направо в списке инициализации в фигурных скобках  
  
 Элементы списка инициализации в фигурных скобках, оцениваются в порядке слева направо. Существует два случая, в которых компилятор не может гарантировать этот порядок: во-первых, если некоторые элементы — это объекты, передаваемые по значению; второй — при компиляции с параметром `/clr` и некоторые элементы являются поля объектов или элементов массива. Когда компилятор не может гарантировать оценки справа налево, она выдает предупреждение C4868.  
  
 Это предупреждение может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2015 г. обновление 2. Перед обновлением 2 Visual C++ 2015 компиляции кода, который будет выдавать C4868.  
  
 Это предупреждение отключено по умолчанию. Используйте `/Wall` для активации этого предупреждения.  
  
 Чтобы устранить это предупреждение, сначала необходимо учитывать слева направо оценки элементов списка инициализаторов обязательно, например при оценки элементов может привести к побочным эффектам зависящих от порядка. Во многих случаях порядок, в котором вычисляются элементов не имеет видимой активности.  
  
 Если порядок вычисления должно быть справа налево, попробуйте использовать его можно передать элементы по ссылке (const) вместо. Изменения, например это устраняет предупреждение в следующем образце кода.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4868.  
  
```  
// C4868.cpp  
// compile with: /c /Wall  
#include <cstdio>  
  
class HasCopyConstructor  
{  
public:  
    int x;  
  
    HasCopyConstructor(int x): x(x) {}  
  
    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)  
    {  
        printf("Constructing %d\n", h.x);  
    }  
};  
  
class TripWarning4868  
{  
public:  
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.  
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}  
  
    // This variation will not trigger the warning:  
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}  
};  
  
int main()  
{  
    HasCopyConstructor a{1};  
    HasCopyConstructor b{2};  
  
    // the warning will indicate the below line, the usage of the braced initializer list.  
    TripWarning4868 warningOnThisLine{a, b};  
};  
```
