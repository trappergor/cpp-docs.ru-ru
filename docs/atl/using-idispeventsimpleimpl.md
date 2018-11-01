---
title: Использование IDispEventSimpleImpl (ATL)
ms.date: 11/04/2016
f1_keywords:
- IDispEventSimpleImpl
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
ms.openlocfilehash: 4b8b651b9f300d3de87297fc62ba54b549e99001
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538272"
---
# <a name="using-idispeventsimpleimpl"></a>Использование IDispEventSimpleImpl

При использовании `IDispEventSimpleImpl` для обработки событий, вам потребуется:

- Наследование класса из [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).

- Добавьте картой приемника событий к классу.

- Определение [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) структур, описывающих события.

- Добавьте записи в карте приемника событий с помощью [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) макрос.

- Реализуйте методы, что вы заинтересованы в обработке.

- Уведомлений и негативной рекомендации источника события.

## <a name="example"></a>Пример

В приведенном ниже примере показано, как обрабатывать `DocumentChange` события, инициированные средой Word **приложения** объекта. Это событие определяется как метод на `ApplicationEvents` disp-интерфейса.

Пример взят из [ATLEventHandling пример](../visual-cpp-samples.md).

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

В примере используется `#import` для создания файлов обязательный заголовок из библиотеки типов в Word. Если вы хотите использовать этот пример с другими версиями Word, необходимо указать правильный mso dll-файла. Например Office 2000 предоставляет mso9.dll и OfficeXP предоставляет mso.dll. Этот код является упрощенной версией stdafx.h:

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

Единственные сведения из библиотеки типов, фактически используемый в этом примере — это CLSID слова `Application` объекта и идентификатор IID `ApplicationEvents` интерфейс. Эта информация используется только во время компиляции.

В Simple.h отображается следующий код. Соответствующий код указан с комментариями:

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

Следующий код является из Simple.cpp:

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>См. также

[Обработка событий](../atl/event-handling-and-atl.md)<br/>
[Пример ATLEventHandling](../visual-cpp-samples.md)

