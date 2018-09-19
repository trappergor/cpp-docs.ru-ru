---
title: Ошибка вычислителя выражений CXX0064 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b16133484af5a2225f79c5d293a2c8edd948bdb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025897"
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