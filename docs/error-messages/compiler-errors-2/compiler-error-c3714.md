---
title: Ошибка компилятора C3714
ms.date: 11/04/2016
f1_keywords:
- C3714
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
ms.openlocfilehash: 9bfdf8b26ab599ef1a28483af7ebc28f0dbc1912
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441877"
---
# <a name="compiler-error-c3714"></a>Ошибка компилятора C3714

«метод»: метод обработчика событий должен возвращать соглашение о вызове, как и исходный «метод»

Вы определили метод обработчика событий, в котором не используется соглашение о вызове как исходный метод события. Чтобы устранить эту ошибку, присвойте методу обработчика событий же соглашения о вызовах что и исходный метод события. Например, в приведенном ниже коде сделать соглашение о вызовах `handler1` и `event1` соответствуют ([__cdecl](../../cpp/cdecl.md) или [__stdcall](../../cpp/stdcall.md) или другим пользователям). Удаление вызов соглашение ключевые слова из обоих объявлениях, могут также решить проблему и вызвать `event1` и `handler1` для использования по умолчанию [thiscall](../../cpp/thiscall.md) соглашение о вызовах. См. в разделе [соглашения о вызовах](../../cpp/calling-conventions.md) Дополнительные сведения.

Следующий пример приводит к возникновению ошибки C3714:

```
// C3714.cpp
// compile with: /c
// processor: x86
[event_source(native)]
class CEventSrc {
public:
   __event void __cdecl event1();
   // try the following line instead
   // __event void __stdcall event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void __stdcall handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714
   }
};
```