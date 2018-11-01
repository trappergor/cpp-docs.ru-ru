---
title: Ошибка компилятора C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 86c043889c5342ed4f3edfc4d8a298bcbd345b3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456398"
---
# <a name="compiler-error-c3765"></a>Ошибка компилятора C3765

«событие»: не удается определить события в классе или структуре «тип» с пометкой event_receiver

Если класс, помеченный с [event_receiver](../../windows/event-receiver.md) атрибут, не может содержать класс [__event](../../cpp/event.md) объявления.

В следующем примере возникает ошибка C3765:

```
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```