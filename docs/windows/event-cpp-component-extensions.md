---
title: "event (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "event"
  - "event_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event - ключевое слово [C++]"
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
caps.latest.revision: 34
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# event (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `event` объявляет *событие*, которое является уведомлением для зарегистрированных подписчиков \(*обработчиков событий*\) о том, что произошло нечто интересное.  
  
## Все среды выполнения  
 C\+\+\/CX поддерживает объявление *члена события* или *блока событий*.  Член события является сокращением для объявления блока событий.  По умолчанию член события объявляет функции `add()`, `remove()` и `raise()`, явно объявленные в блоке событий.  Для настройки функций в члене события объявите блок событий и затем переопределите нужные вам функции.  
  
 **Синтаксис**  
  
```  
  
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
  
 **Параметры**  
  
 *modifier*  
 Модификатор, который может использоваться в объявлении события или в методе доступа события.  Возможными значениями являются `static` и `virtual`.  
  
 *delegate*  
 [Делегат](../windows/delegate-cpp-component-extensions.md), сигнатуре которого должен соответствовать обработчик событий.  
  
 *event\_name*  
 Имя события.  
  
 *return\_value*  
 Возвращаемое значение метода доступа события.  Чтобы возвращаемое значение было проверяемым, его тип должен быть `void`.  
  
 *parameters*  
 \(Необязательно.\) Параметры для метода `raise`, соответствующие сигнатуре параметра *delegate*.  
  
 **Примечания**  
  
 Событие — это связь между делегатом и функцией\-членом \(обработчиком событий\), которая отвечает за инициацию события и позволяет клиентам из любого класса регистрировать методы, соответствующие сигнатуре и типу возвращаемого значения базового делегата.  
  
 Существует два вида объявлений событий.  
  
 *Элемент данных события*  
 Компилятор автоматически создает хранилище для события в виде члена типа делегата и создает внутренние функции\-члены `add()`, `remove()` и `raise()`.  Элемент данных события должен объявляться внутри класса.  Тип возвращаемого значения типа возвращаемого значения делегата должен соответствовать типу возвращаемого значения обработчика событий.  
  
 *Блок событий*  
 Блок событий позволяет явно объявить и настроить поведение методов `add()`, `remove()` и `raise()`.  
  
 Вы можете использовать `operators+=` и `operator-=` для добавления и удаления обработчика событий или для явного вызова методов `add()` и `remove()`.  
  
 `event` — контекстно\-зависимое ключевое слово; дополнительные сведения см. в разделе [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Примечания  
 Дополнительные сведения см. в разделе [События \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755799.aspx).  
  
 Если вы собираетесь добавить и затем удалить обработчик событий, необходимо сохранить структуру EventRegistrationToken, возвращаемую операцией добавления.  Затем в операции удаления необходимо использовать сохраненную структуру EventRegistrationToken для определения удаляемого обработчика событий.  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Ключевое слово `event` позволяет объявить событие.  Событие — это способ, которым класс предоставляет уведомление о том, что произошло нечто интересное.  
  
 **Синтаксис**  
  
```  
  
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
  
 **Параметры**  
  
 *modifier*  
 Модификатор, который может использоваться в объявлении события или в методе доступа события.  Возможными значениями являются `static` и `virtual`.  
  
 *delegate*  
 [Делегат](../windows/delegate-cpp-component-extensions.md), сигнатуре которого должен соответствовать обработчик событий.  
  
 *event\_name*  
 Имя события.  
  
 *return\_value*  
 Возвращаемое значение метода доступа события.  Чтобы возвращаемое значение было проверяемым, его тип должен быть `void`.  
  
 *parameters*  
 \(Необязательно.\) Параметры для метода `raise`, соответствующие сигнатуре параметра *delegate*.  
  
 **Примечания**  
  
 Событие — это связь между делегатом и функцией\-членом \(обработчиком событий\), которая отвечает за инициацию события и позволяет клиентам из любого класса регистрировать методы, соответствующие сигнатуре и типу возвращаемого значения базового делегата.  
  
 Делегат может иметь один или несколько связанных методов, вызываемых, когда код указывает, что произошло событие.  Событие в одной программе можно сделать доступным для других программ, предназначенных для среды CLR .NET Framework.  Пример см. в разделе [Вызов события, определенного в другой сборке](../misc/how-to-raise-events-defined-in-a-different-assembly.md).  
  
 Существует два вида объявлений событий.  
  
 *Элементы данных события*  
 Хранилище для события в виде члена типа делегата создается компилятором для событий элементов данных.  Элемент данных события должен объявляться внутри класса.  Он также называется простым событием \(см. пример кода ниже\).  
  
 *Блоки событий*  
 Блоки событий позволяют настраивать поведение методов добавления, удаления и порождения путем реализации методов добавления, удаления и порождения.  Сигнатура методов добавления, удаления и порождения должна соответствовать сигнатуре делегата.  События блока событий не являются элементами данных, и любое их использование в качестве элемента данных приведет к ошибке компилятора.  Пример см. в разделе [Определение методов доступа к событию](../misc/how-to-define-event-accessor-methods.md).  
  
 Возвращаемый тип обработчика события должен соответствовать возвращаемому типу делегата.  
  
 В платформе .NET Framework данные\-член можно рассматривать, как если бы это был сам метод \(т. е., метод `Invoke` соответствующего делегата\).  Необходимо заранее определить тип делегата для объявления данных\-члена управляемого события.  Напротив, метод управляемого события неявно определяет соответствующий управляемый делегат, если он еще не определен.  См. пример кода в конце этого раздела.  
  
 При объявлении управляемого события можно указать методы доступа добавления и удаления, которые будут вызываться в случае добавления или удаления обработчиков события с помощью операторов \+\= и \-\=.  Методы добавления, удаления и порождения могут вызываться явно.  
  
 Для создания и использования событий в Visual C\+\+ необходимо выполнить следующие действия.  
  
1.  Создать или определить делегат.  При определении собственных событий необходимо также убедиться, что существует делегат для использования с ключевым словом `event`.  Если событие является предопределенным, например в .NET Framework, то потребителям этого события нужно знать только имя делегата.  
  
2.  Создать класс, содержащий следующие объекты.  
  
    -   Событие, созданное из делегата.  
  
    -   \(Необязательно.\) Метод, который проверяет, что экземпляр делегата, объявленный с ключевым словом `event`, существует.  В противном случае эту логику необходимо разместить в коде, который инициирует событие.  
  
    -   Методы, которые вызывают события.  Эти методы могут быть переопределениями некоторых функциональных возможностей базового класса.  
  
     Этот класс определяет событие.  
  
3.  Определить один или несколько классов, которые связывают методы с событием.  Каждый из этих классов будет связывать один или несколько методов с событием в базовом классе.  
  
4.  Использовать событие.  
  
    -   Создать объект класса, содержащего объявление события.  
  
    -   Создать объект класса, содержащего определение события.  
  
 Дополнительные сведения о событиях [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] см. в следующих разделах.  
  
-   [События в интерфейсе](../dotnet/how-to-use-events-in-cpp-cli.md)  
  
-   [Переопределение доступа по умолчанию методов добавления, удаления и порождения](../misc/how-to-override-default-access-of-add-remove-and-raise-methods.md)  
  
-   [Несколько обработчиков события](../misc/how-to-add-multiple-handlers-to-events.md)  
  
-   [Управляемые виртуальные события](../misc/how-to-implement-managed-virtual-events.md)  
  
-   [Методы доступа к событиям](../misc/how-to-define-event-accessor-methods.md)  
  
-   [Статические события](../Topic/How%20to:%20Define%20and%20Use%20Static%20Events.md)  
  
-   [Вызов события, определенного в другой сборке](../misc/how-to-raise-events-defined-in-a-different-assembly.md)  
  
-   [Абстрактные события](../misc/how-to-implement-abstract-events.md)  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере кода демонстрируется объявление пар делегатов, событий и обработчиков событий; подписка \(добавление\) обработчиков событий; вызов обработчиков событий и затем отмена подписки \(удаление\) обработчиков событий.  
  
```  
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
  
 **Вывод**  
  
  **OnClick: 7, 3.14159**  
 **OnDblClick: Hello** **Пример**  
  
 В следующем примере кода демонстрируется логика, используемая для создания метода `raise` простого события: если событие имеет одного или нескольких подписчиков, при вызове метода `raise` явно или неявно вызывается делегат.  Если типом возвращаемого значения делегата не является `void` и если отсутствуют подписчики на событие, метод `raise` возвращает значение по умолчанию для типа делегата.  Если подписчики на событие отсутствуют, вызов метода `raise` просто возвращается и исключение не вызывается.  Если типом возвращаемого значения делегата не является `void`, возвращается тип делегата.  
  
```  
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
  
 **Вывод**  
  
  **0**  
 **688**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)