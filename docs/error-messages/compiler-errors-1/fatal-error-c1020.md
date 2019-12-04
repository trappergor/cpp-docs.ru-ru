---
title: Неустранимая ошибка C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: 67cf5067c85d07215f6391d9e5d3d1bcb4978e42
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756907"
---
# <a name="fatal-error-c1020"></a>Неустранимая ошибка C1020

непредвиденный #endif

Директива `#endif` не имеет соответствующей директивы `#if`, `#ifdef`или `#ifndef` . Убедитесь, что каждая директива `#endif` имеет соответствующую директиву.

В следующем примере возникает ошибка C1020:

```cpp
// C1020.cpp
#endif     // C1020
```

Возможное решение

```cpp
// C1020b.cpp
// compile with: /c
#if 1
#endif
```
