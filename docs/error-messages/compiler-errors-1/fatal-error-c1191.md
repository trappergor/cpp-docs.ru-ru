---
title: Неустранимая ошибка C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: 89af73699120ee4d8af3cda746727d758ef6d22c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228888"
---
# <a name="fatal-error-c1191"></a>Неустранимая ошибка C1191

«dll» можно импортировать только в глобальной области видимости

Инструкции для импорта библиотеки mscorlib.dll в программе, которая использует программирование/CLR не может находиться в пространстве имен или функции, но должны находиться в глобальной области.

Следующий пример приводит к возникновению ошибки C1191:

```
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

Возможное решение

```
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```