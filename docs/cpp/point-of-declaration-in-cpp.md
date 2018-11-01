---
title: Точка объявления в C++
ms.date: 11/04/2016
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
ms.openlocfilehash: d6cb4c3813d88c8b29fbcb2e0827805f406e6c81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560659"
---
# <a name="point-of-declaration-in-c"></a>Точка объявления в C++

Имя считается объявленным сразу после его декларатора, но перед его (необязательным) инициализатором. (Дополнительные сведения о деклараторах см. в разделе [объявления и определения](declarations-and-definitions-cpp.md).)

Рассмотрим следующий пример.

```cpp
// point_of_declaration1.cpp
// compile with: /W1
double dVar = 7.0;
int main()
{
   double dVar = dVar;   // C4700
}
```

Если точка объявления располагалась *после* инициализацию, то локальная `dVar` инициализировалась 7,0 — значением глобальной переменной `dVar`. Поскольку это не так, `dVar` инициализируется неопределенным значением.

## <a name="see-also"></a>См. также

[Область](../cpp/scope-visual-cpp.md)