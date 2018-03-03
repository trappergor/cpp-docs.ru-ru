---
title: "C4868 Предупреждение компилятора | Документы Microsoft"
ms.date: 10/26/2017
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 261e826043a4f922902de91573a16707897ae6b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4868"></a>Компилятор C4868 предупреждение (уровень 4)

> "_файл_(*номер_строки*)" компилятор не может принудительно применить порядок вычисления слева направо в списке инициализации в фигурных скобках

Элементы списка инициализации в фигурных скобках, оцениваются в порядке слева направо. Существует два случая, в которых компилятор не может гарантировать этот порядок: во-первых, если некоторые элементы являются объектами, передаваемым по значению; второй — при компиляции с параметром `/clr` и некоторые из элементов поля объектов или элементов массива. Когда компилятор не может гарантировать оценки слева направо он создает предупреждение C4868.

Это предупреждение может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2015 с обновлением 2. Код, скомпилированный в версии до Visual C++ 2015 с обновлением 2 теперь могут создавать C4868.

Это предупреждение отключено по умолчанию. Используйте `/Wall` для активации этого предупреждения.

Чтобы устранить это предупреждение, сначала необходимо учитывайте слева направо оценки элементов списка инициализаторов необходимости, например когда оценки элементов может привести к побочные эффекты зависит от порядка сортировки. Во многих случаях порядок, в котором вычисляются элементов имеет заметный эффект.

Если порядок выполнения должны быть справа налево, рассмотрите возможность Если существует возможность передавать элементы по `const` вместо этого используйте ссылки. Изменения, такие как это позволяет устранить предупреждение в следующем образце кода.

## <a name="example"></a>Пример

В этом примере приводит к возникновению ошибки C4868 и показывает способ по ее устранению.

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