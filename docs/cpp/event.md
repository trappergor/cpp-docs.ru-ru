---
title: __event
description: Узнайте, как использовать ключевое слово расширения Microsoft C++ `__event` для обработки собственных событий.
ms.date: 11/20/2020
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.openlocfilehash: 1678699d9b66c1a49dd5ca2bb019a6229c37a031
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483150"
---
# <a name="__event-keyword"></a>`__event` This

Объявление события.

> [!NOTE]
> Атрибуты событий в машинном коде C++ несовместимы со стандартным C++. Они не компилируются при указании [`/permissive-`](../build/reference/permissive-standards-conformance.md) режима соответствия.

## <a name="syntax"></a>Синтаксис

> **`__event`** *`member-function-declarator`* **`;`**\
> **`__event`** **`__interface`** *`interface-specifier`* **`;`**\
> **`__event`** *`data-member-declarator`* **`;`**

## <a name="remarks"></a>Комментарии

Ключевое слово Microsoft **`__event`** может быть применено к объявлению функции-члена, объявлению интерфейса или объявлению члена данных. Однако нельзя использовать **`__event`** ключевое слово для уточнения члена вложенного класса.

В зависимости от того, являются ли источник и получатель события неуправляемыми объектами C++, объектами COM или управляемыми объектами (в .NET Framework), в качестве событий можно использовать следующие конструкции:

| Машинный C++ | COM | Управляемый (.NET Framework) |
|--|--|--|
| функция-член | - | method |
| - | interface | - |
| - | - | элемент данных |

Используйте [`__hook`](../cpp/hook.md) в приемнике событий, чтобы связать функцию-член обработчика с функцией-членом события. После создания события с **`__event`** ключевым словом все обработчики событий, подключенные к этому событию, будут вызываться при вызове события.

**`__event`** Объявление функции-члена не может иметь определения; определение неявно создается, поэтому функцию-член события можно вызвать так, как если бы она была обычной функцией-членом.

> [!NOTE]
> Шаблонный класс или структура не может содержать события.

## <a name="native-events"></a>Собственные события

Собственные события — это функции элементов. Тип возвращаемого значения обычно `HRESULT` или **`void`** , но может быть любым целочисленным типом, включая **`enum`** . Если событие использует целочисленный тип возвращаемого значения, условие ошибки определяется, когда обработчик событий возвращает ненулевое значение. В этом случае событие, которое вызывается, вызывает другие делегаты.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

Пример кода см. [в разделе Обработка событий в машинном коде C++](../cpp/event-handling-in-native-cpp.md) .

## <a name="com-events"></a>COM-события

События COM являются интерфейсами. Параметры функции-члена в интерфейсе источника события должны быть *в* параметрах, но не строго применены. Это обусловлено тем, что параметр *out* не полезен при многоадресной рассылке. Если используется параметр *out* , выдается предупреждение уровня 1.

Тип возвращаемого значения обычно `HRESULT` или **`void`** , но может быть любым целочисленным типом, включая **`enum`** . Если событие использует целочисленный возвращаемый тип, а обработчик событий возвращает ненулевое значение, это может быть условие ошибки. Вызванное событие прерывает вызовы других делегатов. Компилятор автоматически помечает интерфейс источника события как [`source`](../windows/attributes/source-cpp.md) в созданном IDL.

[`__interface`](../cpp/interface.md)Ключевое слово всегда требуется после **`__event`** для источника события com.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

Пример кода см. [в разделе Обработка событий в com](../cpp/event-handling-in-com.md) .

## <a name="managed-events"></a>Управляемые события

Дополнительные сведения о создании кода событий в новом синтаксисе см. в разделе [event](../extensions/event-cpp-component-extensions.md).

Управляемые события — это элементы данных или функции элементов. При использовании с событием тип возвращаемого значения делегата должен соответствовать [спецификации CLS](/dotnet/standard/language-independence-and-language-independent-components). Возвращаемый тип обработчика события должен соответствовать возвращаемому типу делегата. Дополнительные сведения о делегатах см. в разделе [делегаты и события](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md). Если управляемое событие является данными-членом, его тип должен быть указателем на делегат.

В платформе .NET Framework данные-член можно рассматривать, как если бы это был сам метод (т. е., метод `Invoke` соответствующего делегата). Для этого необходимо определить тип делегата для объявления члена данных управляемого события. В отличие от этого, метод управляемого события неявно определяет соответствующий управляемый делегат, если он еще не определен. Например, значение события, такое как `OnClick`, можно объявить как событие следующим образом:

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

При неявном объявлении управляемого события можно указать `add` `remove` методы доступа и, которые вызываются при добавлении или удалении обработчиков событий. Можно также определить функцию-член, которая вызывает (вызывает) событие извне класса.

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

## <a name="see-also"></a>См. также

[Словами](../cpp/keywords-cpp.md)\
[Обработка событий](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
