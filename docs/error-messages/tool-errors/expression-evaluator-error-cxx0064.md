---
title: Ошибка вычислителя выражений CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: f763754299ed9257fb909b49a7a19c6f3ad58681
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184467"
---
# <a name="expression-evaluator-error-cxx0064"></a>Ошибка вычислителя выражений CXX0064

не удается задать точку останова для привязанной виртуальной функции члена

Точка останова была задана для виртуальной функции-члена с помощью указателя на объект, например:

```
pClass->vfunc( int );
```

Точку останова можно задать для виртуальной функции, введя класс, например:

```
Class::vfunc( int );
```

Эта ошибка идентична CAN0064.
