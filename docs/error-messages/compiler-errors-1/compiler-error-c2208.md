---
title: Ошибка компилятора C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 7970ba5d8d2b19bd6e330fad1879880fc5cbf32d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516952"
---
# <a name="compiler-error-c2208"></a>Ошибка компилятора C2208

«Тип»: нет членов, определенных с помощью этого типа

— Идентификатор, разрешающийся в имя типа в объявлении агрегата, но компилятор не может объявить элемент.

Следующий пример приводит к возникновению ошибки C2208:

```
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```