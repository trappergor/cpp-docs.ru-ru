---
title: "__event | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __event_cpp
- __event
dev_langs: C++
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4750d156ef4f0f817e1eecec1f4a0842fc229046
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="event"></a>__event
Объявление события.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `__event` может быть применено к объявлению метода, объявлению интерфейса или объявлению данных-членов. Однако ключевое слово `__event` не может использоваться для уточнения члена вложенного класса.  
  
 В зависимости от того, являются ли источник и получатель события неуправляемыми объектами C++, объектами COM или управляемыми объектами (в .NET Framework), в качестве событий можно использовать следующие конструкции:  
  
|Неуправляемый C++|COM|Управляемый (.NET Framework)|  
|------------------|---------|--------------------------------|  
|Метод|—|метод|  
|—|интерфейс|—|  
|—|—|данные-член|  
  
 Используйте [__hook](../cpp/hook.md) в приемнике событий можно связать метод обработчика с методом события. Обратите внимание, что после создания события с помощью ключевого слова `__event` в случае вызова этого события последовательно вызываются все обработчики событий, связанные с этим событием.  
  
 Объявление метода `__event` не может иметь определения; определение создается неявно, поэтому метод события может вызываться, как если бы он был обычным методом.  
  
> [!NOTE]
>  Класс-шаблон или структура не могут содержать события.  
  
## <a name="native-events"></a>Собственные события  
 Собственные события являются методами. Обычно они возвращают тип `HRESULT` или `void`, но может возвращаться любой целочисленный тип, включая `enum`. Если событие использует целочисленный тип возвращаемого значения, условие ошибки определяется как возврат обработчиком события ненулевого значения — в этом случае возникшее событие вызывает другие делегаты.  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 В разделе [обработка событий в неуправляемом коде C++](../cpp/event-handling-in-native-cpp.md) пример кода.  
  
## <a name="com-events"></a>События COM  
 События COM являются интерфейсами. Параметры метода в интерфейсе источника событий должны быть **в** параметров (но это не применяется принудительно тщательно), так как **out** параметр не может использоваться при многоадресной рассылки. Будет выдано предупреждение уровня 1, при использовании **out** параметра.  
  
 Обычно возвращается тип `HRESULT` или `void`, но может возвращаться любой целочисленный тип, включая `enum`. Если событие использует целочисленный тип возвращаемого значения и обработчик события возвращает ненулевое значение, это состояние ошибки, в котором возникшее событие прерывает вызовы других делегатов. Обратите внимание, что компилятор автоматически пометит интерфейс источника события как [источника](../windows/source-cpp.md) в созданном IDL.  
  
 [__Interface](../cpp/interface.md) ключевое слово всегда является обязательным после `__event` для источника событий модели COM.  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 В разделе [обработка событий в COM](../cpp/event-handling-in-com.md) пример кода.  
  
## <a name="managed-events"></a>Управляемые события  
 Сведения о написании кода события в новом синтаксисе см. в разделе [событие](../windows/event-cpp-component-extensions.md).  
  
 Управляемые события являются данными-членами или методами. При использовании с событием тип возвращаемого значения делегата должен соответствовать [спецификации CLS](/dotnet/standard/language-independence-and-language-independent-components). Тип возвращаемого значения обработчика события должен соответствовать возвращаемому типу делегата. Дополнительные сведения о делегатах см. в разделе [делегатов и событий](../dotnet/delegates-and-events.md). Если управляемое событие является данными-членом, его тип должен быть указателем на делегат.  
  
 В платформе .NET Framework данные-член можно рассматривать, как если бы это был сам метод (т. е., метод `Invoke` соответствующего делегата). Необходимо заранее определить тип делегата для объявления данных-члена управляемого события. Напротив, метод управляемого события неявно определяет соответствующий управляемый делегат, если он еще не определен. Например, значение события, такое как `OnClick`, можно объявить как событие следующим образом:  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 При неявном объявлении управляемого события можно указать методы доступа добавления и удаления, которые будут вызываться в случае добавления или удаления обработчиков события. Можно также определить метод, который вызывает событие вне класса.  
  
## <a name="example-native-events"></a>Пример: собственные события  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## <a name="example-com-events"></a>Пример: события COM  
  
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
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Обработка событий](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)