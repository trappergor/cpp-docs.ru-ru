---
title: __event
ms.date: 11/04/2016
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
ms.openlocfilehash: f8935408c6e9b43347d4ad6088505a461e254ae2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366304"
---
# <a name="__event"></a>__event

Объявление события.

## <a name="syntax"></a>Синтаксис

```
__event method-declarator;
__event __interface interface-specifier;
__event member-declarator;
```

## <a name="remarks"></a>Remarks

Ключевое слово **__event** может быть применено к декларации метода, декларации интерфейса или декларации члена данных. Тем не менее, вы не можете использовать ключевое слово **__event,** чтобы квалифицировать члена вложенного класса.

В зависимости от того, являются ли источник и получатель события неуправляемыми объектами C++, объектами COM или управляемыми объектами (в .NET Framework), в качестве событий можно использовать следующие конструкции:

|Машинный C++|COM|Управляемый (.NET Framework)|
|------------------|---------|--------------------------------|
|Метод|—|method|
|—|interface|—|
|—|—|элемент данных|

Используйте [__hook](../cpp/hook.md) в приемнике событий, чтобы связать метод обработчика с методом события. Обратите внимание, что после создания события с ключевым словом **__event** все обработчики событий впоследствии будут вызваны при вызове события.

Декларация **__event** метода не может иметь определения; определение неявно генерируется, поэтому метод события можно назвать как обычный метод.

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="native-events"></a>Собственные события

Собственные события являются методами. Тип возврата, как правило, HRESULT или **недействительным,** но может быть любой интегральный тип, в том числе **enum**. Если событие использует целочисленный тип возвращаемого значения, условие ошибки определяется как возврат обработчиком события ненулевого значения — в этом случае возникшее событие вызывает другие делегаты.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

Посмотреть [обработку событий в Native C ,](../cpp/event-handling-in-native-cpp.md) чтобы ознакомиться с образцами кода.

## <a name="com-events"></a>События COM

События COM являются интерфейсами. Параметры метода в интерфейсе источника событий должны быть *в* параметрах (но это не строго соблюдается), потому что параметр *из* не полезен при мультикастинге. Предупреждение уровня 1 будет выпущено, если вы *используете* из параметра.

Тип возврата, как правило, HRESULT или **недействительным,** но может быть любой интегральный тип, в том числе **enum**. Если событие использует целочисленный тип возвращаемого значения и обработчик события возвращает ненулевое значение, это состояние ошибки, в котором возникшее событие прерывает вызовы других делегатов. Обратите внимание, что компилятор автоматически пометит интерфейс источника событий в качестве [источника](../windows/attributes/source-cpp.md) в генерируемом IDL.

Ключевое слово [__interface](../cpp/interface.md) всегда требуется после **__event** для источника событий COM.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

Смотрите [обработку событий в COM](../cpp/event-handling-in-com.md) для образца кода.

## <a name="managed-events"></a>Управляемые события

Для получения информации о событиях кодирования [event](../extensions/event-cpp-component-extensions.md)в новом синтаксисе см.

Управляемые события являются данными-членами или методами. При использовании события тип возврата делегата должен соответствовать [спецификации общего языка.](/dotnet/standard/language-independence-and-language-independent-components) Возвращаемый тип обработчика события должен соответствовать возвращаемому типу делегата. Для получения дополнительной информации о делегатах, [см.](../dotnet/delegates-and-events.md) Если управляемое событие является данными-членом, его тип должен быть указателем на делегат.

В платформе .NET Framework данные-член можно рассматривать, как если бы это был сам метод (т. е., метод `Invoke` соответствующего делегата). Необходимо заранее определить тип делегата для объявления данных-члена управляемого события. Напротив, метод управляемого события неявно определяет соответствующий управляемый делегат, если он еще не определен. Например, значение события, такое как `OnClick`, можно объявить как событие следующим образом:

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

При неявном объявлении управляемого события можно указать методы доступа добавления и удаления, которые будут вызываться в случае добавления или удаления обработчиков события. Можно также определить метод, который вызывает событие вне класса.

## <a name="example-native-events"></a>Пример: собственные события

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>Пример: события COM

```cpp
// EventHandling_COM_Event.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT MyEvent();
};
[ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]
class CSource : public IEventSource {
public:
   __event __interface IEventSource;
   HRESULT FireEvent() {
      __raise MyEvent();
      return S_OK;
   }
};
```

## <a name="see-also"></a>См. также раздел

[Keywords](../cpp/keywords-cpp.md)<br/>
[Обработка событий](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)
