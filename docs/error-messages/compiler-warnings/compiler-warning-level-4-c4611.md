---
title: Предупреждение компилятора (уровень 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: 2ce261b36344126d541a9b453c88f7f8289ecba0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214338"
---
# <a name="compiler-warning-level-4-c4611"></a>Предупреждение компилятора (уровень 4) C4611

взаимодействие между "Function" и "уничтожением объектов C++" не является переносимым

На некоторых платформах функции, которые включают, **`catch`** могут не поддерживать семантику объектов C++ при выходе из области действия.

Чтобы избежать непредвиденного поведения, Избегайте использования **`catch`** в функциях, имеющих конструкторы и деструкторы.

Это предупреждение выдается только один раз. см. [предупреждение pragma](../../preprocessor/warning.md).
