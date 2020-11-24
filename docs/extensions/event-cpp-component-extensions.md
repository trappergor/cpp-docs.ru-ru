---
title: ключевое слово Event (C++/CLI и C++/CX)
description: Узнайте, как использовать ключевое слово расширений Microsoft C++ Component Extensions `event` .
ms.date: 11/20/2020
ms.topic: reference
f1_keywords:
- event
- event_cpp
helpviewer_keywords:
- event keyword [C++]
ms.openlocfilehash: 6a2fa97140f747b4afc380b57f8f7c71f08875db
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483247"
---
# <a name="event-keyword-ccli-and-ccx"></a>`event` ключевое слово (C++/CLI и C++/CX)

**`event`** Ключевое слово объявляет *событие*, которое является уведомлением зарегистрированных подписчиков (*обработчиков событий*) о том, что возникли какие-либо интересы.

## <a name="all-runtimes"></a>Все среды выполнения

C++/CX поддерживает объявление *элемента события* или *блока событий*. Член события является сокращением для объявления блока событий. По умолчанию член события объявляет функции `add`, `remove` и `raise`, явно объявленные в блоке событий. Для настройки функций в члене события объявите блок событий и затем переопределите нужные вам функции.

### <a name="syntax"></a>Синтаксис

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>Параметры

*Модификатор*\
Модификатор, который может использоваться в объявлении события или в методе доступа события.  Возможные значения: **`static`** и **`virtual`** .

*получить*\
[Делегат](delegate-cpp-component-extensions.md), сигнатура которого должна соответствовать обработчику событий.

*event_name*\
Имя события.

*return_value*\
Возвращаемое значение метода доступа события.  Чтобы быть проверяемым, возвращаемым типом должен быть **`void`** .

*Вход*\
(Необязательно) Параметры для метода `raise`, соответствующие сигнатуре параметра *delegate*.

### <a name="remarks"></a>Комментарии

Событие — это ассоциация между делегатом и *обработчиком событий*. Обработчик событий — это функция-член, которая реагирует на срабатывание события. Он позволяет клиентам из любого класса регистрировать методы, соответствующие сигнатуре и возвращаемому типу делегата.

Существует два вида объявлений событий.

*элемент данных события*\
Компилятор автоматически создает хранилище для события в виде члена типа делегата и создает внутренние функции-члены `add`, `remove` и `raise`. Элемент данных события должен объявляться внутри класса. Тип возвращаемого значения типа возвращаемого значения делегата должен соответствовать типу возвращаемого значения обработчика событий.

*блок событий*\
Блок событий позволяет явно объявить и настроить поведение методов `add`, `remove` и `raise`.

Можно использовать `operator +=` и `operator -=` для добавления и удаления обработчика событий, а также для `add` явного вызова `remove` методов и.

**`event`** контекстно-зависимое ключевое слово. Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Комментарии

Дополнительные сведения см. в статье [Events (C++/CX)](../cppcx/events-c-cx.md) (События (C++/CX)).

Чтобы добавить и позже удалить обработчик событий, сохраните `EventRegistrationToken` структуру, возвращенную `add` операцией. Затем в `remove` операции используйте сохраненную структуру, `EventRegistrationToken` чтобы указать обработчик событий для удаления.

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

Ключевое слово **event** позволяет объявить событие. Событие — это способ, которым класс предоставляет уведомление о том, что произошло нечто интересное.

### <a name="syntax"></a>Синтаксис

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>Параметры

*Модификатор*\
Модификатор, который может использоваться в объявлении события или в методе доступа события.  Возможные значения: **`static`** и **`virtual`** .

*получить*\
[Делегат](delegate-cpp-component-extensions.md), сигнатура которого должна соответствовать обработчику событий.

*event_name*\
Имя события.

*return_value*\
Возвращаемое значение метода доступа события.  Чтобы быть проверяемым, возвращаемым типом должен быть **`void`** .

*Вход*\
(Необязательно) Параметры для метода `raise`, соответствующие сигнатуре параметра *delegate*.

### <a name="remarks"></a>Комментарии

Событие — это ассоциация между делегатом и *обработчиком событий*. Обработчик событий — это функция-член, которая реагирует на срабатывание события. Он позволяет клиентам из любого класса регистрировать методы, соответствующие сигнатуре и возвращаемому типу базового делегата.

Делегат может иметь один или несколько связанных методов. Эти методы вызываются, когда код указывает, что событие произошло. Событие в одной программе можно сделать доступным для других программ, предназначенных для среды CLR .NET Framework.

Существует два вида объявлений событий:

*элементы данных события*\
Компилятор создает хранилище для событий элементов данных в качестве члена типа делегата. Элемент данных события должен объявляться внутри класса. Он также называется *тривиальным событием*. Пример см. в примере кода.

*блоки событий*\
Блоки событий позволяют настраивать поведение `add` `remove` методов, и `raise` , реализуя `add` `remove` методы, и `raise` . Сигнатура `add` `remove` методов, и `raise` должна соответствовать сигнатуре делегата. События блока событий не являются членами данных. Любое использование в качестве члена данных приводит к ошибке компилятора.

Возвращаемый тип обработчика события должен соответствовать возвращаемому типу делегата.

В платформе .NET Framework данные-член можно рассматривать, как если бы это был сам метод (т. е., метод `Invoke` соответствующего делегата). Для этого необходимо определить тип делегата для объявления члена данных управляемого события. В отличие от этого, метод управляемого события неявно определяет соответствующий управляемый делегат, если он еще не определен. См. пример кода в конце этой статьи.

При объявлении управляемого события можно указать `add` `remove` методы доступа и, которые будут вызываться при добавлении или удалении обработчиков событий с помощью операторов **`+=`** и **`-=`** . `add`Методы, `remove` и `raise` можно вызывать явным образом.

Для создания и использования событий в Microsoft C++ необходимо выполнить следующие действия.

1. Создать или определить делегат. При определении собственного события необходимо также убедиться, что существует делегат, используемый с **`event`** ключевым словом. Если событие является предопределенным, например в .NET Framework, то потребителям этого события нужно знать только имя делегата.

2. Создать класс, содержащий следующие объекты.

   - Событие, созданное из делегата.

   - Используемых Метод, проверяющий, существует ли экземпляр делегата, объявленного с **`event`** ключевым словом. В противном случае эту логику необходимо разместить в коде, который инициирует событие.

   - Методы, которые вызывают события. Эти методы могут быть переопределениями некоторых функциональных возможностей базового класса.

   Этот класс определяет событие.

3. Определить один или несколько классов, которые связывают методы с событием. Каждый из этих классов будет связывать один или несколько методов с событием в базовом классе.

4. Использовать событие.

   - Создать объект класса, содержащего объявление события.

   - Создать объект класса, содержащего определение события.

Дополнительные сведения о событиях C++/CLI см. [в разделе события в интерфейсе](../dotnet/how-to-use-events-in-cpp-cli.md).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода демонстрируется объявление пар делегатов, событий и обработчиков событий. В нем показано, как подписываться (добавлять), вызывать и отменять подписываться (Remove) обработчики событий.

```cpp
// mcppv2_events.cpp
// compile with: /clr
using namespace System;

// declare delegates
delegate void ClickEventHandler(int, double);
delegate void DblClickEventHandler(String^);

// class that defines events
ref class EventSource {
public:
   event ClickEventHandler^ OnClick;   // declare the event OnClick
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick

   void FireEvents() {
      // raises events
      OnClick(7, 3.14159);
      OnDblClick("Hello");
   }
};

// class that defines methods that will called when event occurs
ref class EventReceiver {
public:
   void OnMyClick(int i, double d) {
      Console::WriteLine("OnClick: {0}, {1}", i, d);
   }

   void OnMyDblClick(String^ str) {
      Console::WriteLine("OnDblClick: {0}", str);
   }
};

int main() {
   EventSource ^ MyEventSource = gcnew EventSource();
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();

   // hook handler to event
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);

   // invoke events
   MyEventSource->FireEvents();

   // unhook handler to event
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);
}
```

```Output
OnClick: 7, 3.14159

OnDblClick: Hello
```

В следующем примере кода показана логика, используемая для создания `raise` метода тривиального события. Если событие имеет один или несколько подписчиков, при вызове метода `raise` явно или неявно вызывается делегат. Если тип возвращаемого значения делегата не **`void`** равен и если есть подписчики на события, `raise` метод возвращает значение по умолчанию для типа делегата. Если подписчики на события отсутствуют, вызов `raise` метода немедленно возвращает значение и исключение не возникает. Если тип возвращаемого значения делегата не **`void`** имеет значение, возвращается тип делегата.

```cpp
// trivial_events.cpp
// compile with: /clr /c
using namespace System;
public delegate int Del();
public ref struct C {
   int i;
   event Del^ MyEvent;

   void FireEvent() {
      i = MyEvent();
   }
};

ref struct EventReceiver {
   int OnMyClick() { return 0; }
};

int main() {
   C c;
   c.i = 687;

   c.FireEvent();
   Console::WriteLine(c.i);
   c.i = 688;

   EventReceiver^ MyEventReceiver = gcnew EventReceiver();
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);
   Console::WriteLine(c.i);
}
```

```Output
0

688
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
