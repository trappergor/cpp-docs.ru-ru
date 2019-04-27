---
title: Точка объявления в C++
ms.date: 11/04/2016
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
ms.openlocfilehash: d6cb4c3813d88c8b29fbcb2e0827805f406e6c81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183405"
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