---
title: Предупреждение компилятора C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: d0bc8716e53e71c52f6a31036a95d0b4cefedd79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481321"
---
# <a name="compiler-warning-level-4-c4868"></a>Предупреждение (уровень 4) компилятора C4868

> "_файл_(*номер_строки*)" компилятор не может принудительно применить порядок вычисления слева направо в списке инициализации в фигурных скобках

Элементы списка инициализации в фигурных скобках, оцениваются в порядке слева направо. Существует два случая, в которых компилятор не может гарантировать этот порядок: во-первых, если некоторые элементы являются объектами, передаваемые по значению; второй — при компиляции с параметром `/clr` и некоторые из элементов поля объектов или элементов массива. Когда компилятор не может гарантировать оценки слева направо, он выдает предупреждение C4868.

Это предупреждение может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2015 с обновлением 2. Код, скомпилированный в версии до Visual C++ 2015 с обновлением 2 можно приступить к созданию C4868.

Это предупреждение отключено по умолчанию. Используйте `/Wall` активировать это предупреждение.

Чтобы устранить это предупреждение, сначала рассмотрите возможность оценки слева направо, элементами списка инициализатора необходимости, например когда вычисление элементов может произвести зависящую от порядка побочные эффекты. Во многих случаях порядок, в котором вычисляются элементов имеет значительное влияние.

Если порядок вычисления должен быть слева направо, рекомендуется, если имеется возможность передавать элементы по `const` ссылку. Изменения, такие как это устраняет предупреждение в следующем образце кода.

## <a name="example"></a>Пример

Этот пример создает C4868 и показывает способ ее устранения:

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