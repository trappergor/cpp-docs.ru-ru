---
title: Ошибка компилятора C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: a75ccd9824106f2b954cd090a0e00ab11786d243
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393692"
---
# <a name="compiler-error-c2386"></a>Ошибка компилятора C2386

"символ": символ с таким именем уже существует в текущей области

Предпринята попытка создания псевдонима пространства имен, но выбранное имя уже существует.

Следующий пример приводит к возникновению ошибки C2386:

```
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```