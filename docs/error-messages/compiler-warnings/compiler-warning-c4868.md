---
title: Предупреждение компилятора C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
helpviewer_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: c1d49eb61a5c7c47fa83dacb39ed50f42e0fb147
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810477"
---
# <a name="compiler-warning-level-4-c4868"></a>Предупреждение компилятора (уровень 4) C4868

> Компилятор "_File_(*line_number*)" не может применить порядок вычисления слева направо в списке инициализаторов в фигурных скобках

Элементы списка инициализаторов в фигурных скобках должны вычисляться в порядке слева направо. Существует два варианта, в которых компилятор не может гарантировать этот порядок: первый — когда некоторые из элементов являются объектами, передаваемыми по значению; второй — при компиляции с `/clr`, а некоторые из элементов являются полями объектов или являются элементами массива. Если компилятор не может гарантировать вычисление слева направо, он выдает предупреждение C4868.

Это предупреждение можно создать в результате действий по согласованности компилятора, выполненных для Visual Studio 2015 с обновлением 2. Код, скомпилированный до Visual Studio 2015 с обновлением 2, теперь может создавать C4868.

Это предупреждение отключено по умолчанию. Чтобы активировать это предупреждение, используйте `/Wall`.

Чтобы устранить это предупреждение, сначала необходимо определить, требуется ли вычисление слева направо для элементов списка инициализаторов, например, если вычисление элементов может привести к побочным эффектам, зависящим от порядка. Во многих случаях порядок, в котором оцениваются элементы, не имеет наблюдаемого результата.

Если порядок вычисления должен быть слева направо, подумайте, можно ли передать элементы по `const` ссылке. Такое изменение устраняет предупреждение в следующем примере кода.

## <a name="example"></a>Пример

В этом примере создается C4868 и демонстрируется способ исправления:

```cpp
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