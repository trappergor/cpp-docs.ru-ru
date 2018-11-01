---
title: Ошибка компилятора C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: b52797b945b1a652506b4a85171e60a91544bbf0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546489"
---
# <a name="compiler-error-c2190"></a>Ошибка компилятора C2190

Первый список параметров длиннее второго

Функция C была объявлена во второй раз с более коротким списком параметров. C не поддерживает перегруженные функции.

Следующий пример приводит к возникновению ошибки C2190:

```
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```