---
title: Ошибка компилятора C3710
ms.date: 11/04/2016
f1_keywords:
- C3710
helpviewer_keywords:
- C3710
ms.assetid: 18bec009-5b6f-464a-a21e-5d58a6936504
ms.openlocfilehash: 04b79b3c924892eb2a970f880d3f2048f4cb2b10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607679"
---
# <a name="compiler-error-c3710"></a>Ошибка компилятора C3710

«функция»: неправильный синтаксис для задания обработчика событий в __hook или\__unhook

При указании обработчик событий с [__hook](../../cpp/hook.md) или [__unhook](../../cpp/unhook.md), обработчик должен быть допустимым запросом.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3710

```
// C3710.cpp
// compile with: /link /opt:noref
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>
#include <stdio.h>

[event_source(native)]
class CEventSrc
{
public:
    __event void event1();
};

[event_receiver(native)]
class CEventRec
{
public:
    void handler1()
    {
        printf_s("Executing handler1().\n");
    }

    void HookEvents(CEventSrc* pSrc)
    {
        __hook(&CEventSrc::event1, pSrc, 0);   // C3710
        // try the following line instead
        // __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);
    }

    void UnhookEvents(CEventSrc* pSrc)
    {
        __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);
    }
};

int main()
{
    CEventSrc eventSrc;
    CEventRec eventRec;
    eventRec.HookEvents(&eventSrc);
    eventSrc.event1();
    eventRec.UnhookEvents(&eventSrc);
}
```