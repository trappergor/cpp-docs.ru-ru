---
title: Обработка событий в COM
description: Узнайте, как использовать расширения Microsoft C++ для обработки событий COM.
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++], COM
- event handling [C++], about event handling
- declaring events
- event handlers [C++], COM
- event handlers
- COM, events
- event receivers, in event handling
- event handling [C++]
- hooking events
- event receivers, name and signature matching
- event sources, in event handling
- declaring events, in COM
- declaring events, event handling in COM
ms.openlocfilehash: 0c664f052fe211c88ad097c9d2617ec47f180eff
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483117"
---
# <a name="event-handling-in-com"></a>Обработка событий в COM

При обработке COM-событий вы настраиваете источник события и приемник событий с помощью [`event_source`](../windows/attributes/event-source.md) [`event_receiver`](../windows/attributes/event-receiver.md) атрибутов и соответственно, указывая `type` = `com` . Эти атрибуты вставляют соответствующий код для пользовательских, диспетчеризации и сдвоенных интерфейсов. Внедренный код позволяет классам с атрибутами вызывать события и управлять событиями через точки подключения COM.

> [!NOTE]
> Атрибуты событий в машинном коде C++ несовместимы со стандартным C++. Они не компилируются при указании [`/permissive-`](../build/reference/permissive-standards-conformance.md) режима соответствия.

## <a name="declaring-events"></a>Объявление событий

В классе источника событий используйте [`__event`](../cpp/event.md) ключевое слово в объявлении интерфейса, чтобы объявить методы интерфейса как события. События этого интерфейса запускаются при вызове их в качестве методов интерфейса. Методы в интерфейсах событий могут иметь ноль или более параметров (которые должны быть *в* параметрах). Тип возвращаемого значения может быть пустым или любым целочисленным типом.

## <a name="defining-event-handlers"></a>Определение обработчиков событий

Обработчики событий определяются в классе приемника событий. Обработчики событий — это методы с сигнатурами (возвращаемыми типами, соглашениями о вызовах и аргументами), которые соответствуют событию, которое они будут обработаны. Для COM-событий соглашения о вызовах не должны совпадать. Дополнительные сведения см. в разделе [зависимые от макета события com](#vcconeventhandlingincomanchorlayoutdependentcomevents) ниже.

## <a name="hooking-event-handlers-to-events"></a>Подключение обработчиков событий к событиям

Кроме того, в классе приемника событий используется встроенная функция [`__hook`](../cpp/hook.md) для связывания событий с обработчиками событий и для разрыва [`__unhook`](../cpp/unhook.md) связи между событиями из обработчиков событий. Можно прикрепить несколько событий к обработчику событий либо несколько обработчиков событий к одному событию.

> [!NOTE]
> Как правило, существует два метода предоставления приемнику событий COM доступа к определениям интерфейса исходного кода событий. Во-первых, как показано ниже, можно предоставить общий доступ к одному файлу заголовка. Второй — использовать [#import](../preprocessor/hash-import-directive-cpp.md) с `embedded_idl` квалификатором импорта, чтобы библиотека типов источника событий записывалась в TLH-файл с сохранением сформированного атрибутом кода.

## <a name="firing-events"></a>События, вызывающие срабатывание

Чтобы запустить событие, вызовите метод в интерфейсе, объявленном с помощью **`__event`** ключевого слова в классе источника событий. Если обработчики прикреплены к событию, они будут вызваны.

### <a name="com-event-code"></a>Код события COM

В следующем примере демонстрируется запуск события в COM-классе. Для компиляции и выполнения примера см. комментарии в коде.

```cpp
// evh_server.h
#pragma once

[ dual, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IEvents {
   [id(1)] HRESULT MyEvent([in] int value);
};

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT FireEvent();
};

class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;
```

Затем сервер.

```cpp
// evh_server.cpp
// compile with: /LD
// post-build command: Regsvr32.exe /s evh_server.dll
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include "evh_server.h"

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      __raise MyEvent(123);
      return S_OK;
   }
};
```

Затем клиент.

```cpp
// evh_client.cpp
// compile with: /link /OPT:NOREF
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <stdio.h>
#include "evh_server.h"

[ module(name="EventReceiver") ];

[ event_receiver(com) ]
class CReceiver {
public:
   HRESULT MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
      return S_OK;
   }

   HRESULT MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
      return S_OK;
   }

   void HookEvent(IEventSource* pSource) {
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void UnhookEvent(IEventSource* pSource) {
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   // Create COM object
   CoInitialize(NULL);
   {
      IEventSource* pSource = 0;
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);
      if (FAILED(hr)) {
         return -1;
      }

      // Create receiver and fire event
      CReceiver receiver;
      receiver.HookEvent(pSource);
      pSource->FireEvent();
      receiver.UnhookEvent(pSource);
   }
   CoUninitialize();
   return 0;
}
```

### <a name="output"></a>Выходные данные

```Output
MyHandler1 was called with value 123.
MyHandler2 was called with value 123.
```

## <a name="layout-dependent-com-events"></a><a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> События COM, зависимые от макета

Зависимость от макета становится проблемой только в программировании COM. При обработке собственных и управляемых событий сигнатуры (возвращаемый тип, соглашение о вызовах и аргументы) должны соответствовать своим событиям, но имена обработчиков не должны совпадать с их событиями.

Однако при обработке событий COM, если параметру присвоить значение *`layout_dependent`* `event_receiver` **`true`** , применяется имя и сопоставление подписи. Имена и подписи обработчиков в приемнике событий и в обработчиках событий должны точно совпадать.

Если параметр *`layout_dependent`* имеет значение **`false`** , соглашение о вызовах и класс хранения (виртуальный, статический и т. д.) могут быть смешанными и сопоставлены между методом события обработки и методами обработчика (его делегатами). Это немного более эффективно *`layout_dependent`* = **`true`** .

Например, предположим, что `IEventSource` определен как объект, имеющий следующие методы.

```cpp
[id(1)] HRESULT MyEvent1([in] int value);
[id(2)] HRESULT MyEvent2([in] int value);
```

Предположим, источник событий имеет следующую форму:

```cpp
[coclass, event_source(com)]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      MyEvent1(123);
      MyEvent2(123);
      return S_OK;
   }
};
```

Затем в приемнике событий любой обработчик, который прикрепляется к методу в `IEventSource`, должен соответствовать имени и подписи следующим образом.

```cpp
[coclass, event_receiver(com, true)]
class CReceiver {
public:
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1
      ...
   }
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2
      ...
   }
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)
      ...
   }
   void HookEvent(IEventSource* pSource) {
      __hook(IFace, pSource);  // Hooks up all name-matched events
                               // under layout_dependent = true
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid
   }
};
```

## <a name="see-also"></a>См. также

[Обработка событий](../cpp/event-handling.md)
