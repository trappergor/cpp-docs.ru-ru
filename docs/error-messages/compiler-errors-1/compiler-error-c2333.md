---
title: Ошибка компилятора C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: e9119a8375a276a59cbf3a6db9541f6ccaef5122
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300824"
---
# <a name="compiler-error-c2333"></a>Ошибка компилятора C2333

«функция»: ошибка в объявлении функции; тело функции пропускается

Эта ошибка возникает после другая ошибка, для функций-членов определяемых внутри своего класса.

Следующий пример приводит к возникновению ошибки C2333:

```
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```