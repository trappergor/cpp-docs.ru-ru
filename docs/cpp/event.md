---
title: "__event | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__event_cpp"
  - "__event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__event - ключевое слово [C++]"
  - "события [C++], __event"
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __event
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объявление события.  
  
## Синтаксис  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## Заметки  
 Ключевое слово `__event` может быть применено к объявлению метода, объявлению интерфейса или объявлению данных\-членов.  Однако ключевое слово `__event` не может использоваться для уточнения члена вложенного класса.  
  
 В зависимости от того, являются ли источник и получатель события неуправляемыми объектами C\+\+, объектами COM или управляемыми объектами \(в .NET Framework\), в качестве событий можно использовать следующие конструкции:  
  
|Неуправляемый C\+\+|COM|Управляемый \(.NET Framework\)|  
|-------------------------|---------|------------------------------------|  
|Метод|—|метод|  
|—|интерфейс|—|  
|—|—|данные\-член|  
  
 Используйте [\_\_hook](../cpp/hook.md) в приемнике событий, чтобы связать метод обработчика с методом события.  Обратите внимание, что после создания события с помощью ключевого слова `__event` в случае вызова этого события последовательно вызываются все обработчики событий, связанные с этим событием.  
  
 Объявление метода `__event` не может иметь определения; определение создается неявно, поэтому метод события может вызываться, как если бы он был обычным методом.  
  
> [!NOTE]
>  Класс\-шаблон или структура не могут содержать события.  
  
## Собственные события  
 Собственные события являются методами.  Обычно они возвращают тип `HRESULT` или `void`, но может возвращаться любой целочисленный тип, включая `enum`.  Если событие использует целочисленный тип возвращаемого значения, условие ошибки определяется как возврат обработчиком события ненулевого значения — в этом случае возникшее событие вызывает другие делегаты.  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 Пример кода см. в разделе [Обработка событий в неуправляемом коде C\+\+](../Topic/Event%20Handling%20in%20Native%20C++.md).  
  
## События COM  
 События COM являются интерфейсами.  Параметры метода в интерфейсе источника событий должны быть параметрами **in** \(но строго принудительно это требование не применяется\), так как параметр **out** не может использоваться при многоадресной рассылке.  При использовании параметра **out** выдается предупреждение уровня 1.  
  
 Обычно возвращается тип `HRESULT` или `void`, но может возвращаться любой целочисленный тип, включая `enum`.  Если событие использует целочисленный тип возвращаемого значения и обработчик события возвращает ненулевое значение, это состояние ошибки, в котором возникшее событие прерывает вызовы других делегатов.  Обратите внимание, что компилятор в созданном IDL автоматически помечает интерфейс источника события как [источник](../Topic/source%20\(C++\).md).  
  
 Для источника событий модели COM после ключевого слова `__event` обязательно должно следовать ключевое слово [\_\_interface](../Topic/__interface.md).  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 Пример кода см. в разделе [Обработка событий в модели COM](../cpp/event-handling-in-com.md).  
  
## Управляемые события  
 Дополнительные сведения о кодировании событий в новом синтаксисе см. в разделе [event](../windows/event-cpp-component-extensions.md).  
  
 Управляемые события являются данными\-членами или методами.  При использовании с событием тип возвращаемого значения делегата должен быть совместим со [Спецификаций CLS](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md).  Возвращаемый тип обработчика события должен соответствовать возвращаемому типу делегата.  Дополнительные сведения о делегатах см. в разделе [\_\_delegate](../Topic/__delegate.md).  Если управляемое событие является данными\-членом, его тип должен быть указателем на делегат.  
  
 В платформе .NET Framework данные\-член можно рассматривать, как если бы это был сам метод \(т. е., метод `Invoke` соответствующего делегата\).  Необходимо заранее определить тип делегата для объявления данных\-члена управляемого события.  Напротив, метод управляемого события неявно определяет соответствующий управляемый делегат, если он еще не определен.  Например, значение события, такое как `OnClick`, можно объявить как событие следующим образом:  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 При неявном объявлении управляемого события можно указать методы доступа добавления и удаления, которые будут вызываться в случае добавления или удаления обработчиков события.  Можно также определить метод, который вызывает событие вне класса.  
  
## Пример: собственные события  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## Пример: события COM  
  
```  
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
  
## Пример: управляемые события  
  
```  
// EventHandling_Managed_Event.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[event_source(managed)]  
public __gc class CPSource {  
  
public:  
   __event void MyEvent(Int16 nValue);  
};  
```  
  
 При применении атрибута к событию можно указать, к чему применяется атрибут: к созданным методам или к методу Invoke созданного делегата.  По умолчанию \(`event:`\) атрибут применяется к событию.  
  
```  
// EventHandling_Managed_Event_2.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[attribute(All, AllowMultiple=true)]  
public __gc class Attr {};  
  
public __delegate void D();  
  
public __gc class X {  
public:  
   [method:Attr] __event D* E;  
   [returnvalue:Attr] __event void noE();  
};  
```  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Обработка событий](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)