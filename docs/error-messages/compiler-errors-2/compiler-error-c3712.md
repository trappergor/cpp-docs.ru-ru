---
title: Ошибка компилятора C3712
ms.date: 11/04/2016
f1_keywords:
- C3712
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
ms.openlocfilehash: 0b84f4562dcc0dd5dcc3ecb647316772efab6b38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492681"
---
# <a name="compiler-error-c3712"></a>Ошибка компилятора C3712

«метод»: метод обработчика событий должен возвращать один и тот же тип как источник «метод»

Вы определили метод обработчика событий, который не вернул тот же тип, что и метод источника событий. Чтобы устранить эту ошибку, присвойте методу обработчика событий же тип возвращаемого значения, что и исходный метод события.

Следующий пример приводит к возникновению ошибки C3712:

```
// C3712.cpp
// compile with: /c
[event_source(native)]
class CEventSrc {
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   int handler1() { return 0; }
   // try the following line instead
   // void handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
};
```