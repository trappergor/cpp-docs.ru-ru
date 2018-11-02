---
title: Ошибка вычислителя выражений CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: 71e4e3e87b33849e6b487b79268ebc9574c2e5a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511869"
---
# <a name="expression-evaluator-error-cxx0064"></a>Ошибка вычислителя выражений CXX0064

Невозможно задать точку останова на привязанных виртуальная функция-член

Была задана точка останова на виртуальная функция-член через указатель на объект, например:

```
pClass->vfunc( int );
```

Точки останова можно задать для виртуальной функции путем ввода класса, такие как:

```
Class::vfunc( int );
```

Эта ошибка идентична ошибке CAN0064.