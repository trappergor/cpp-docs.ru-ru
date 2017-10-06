---
title: "__unhook | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unhook
dev_langs:
- C++
helpviewer_keywords:
- event handlers, dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2b1909cf5d7bde440d434bb44ff2276e68679e78
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="unhook"></a>__unhook
Отменяет связь метода обработчика с событием.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      long  __unhook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]   
);  
long  __unhook(   
   interface,  
   source  
);  
long  __unhook(  
   source   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 **&***SourceClass* `::` *EventMethod*  
 Указатель на метод события, с помощью которого отсоединяется метод обработчика событий.  
  
-   События неуправляемого C++: *SourceClass* является исходным классом и *EventMethod* событие.  
  
-   События COM: *SourceClass* — интерфейс источника события и *EventMethod* — один из его методов.  
  
-   Управляемые события: *SourceClass* является исходным классом и *EventMethod* событие.  
  
 `interface`  
 Имя интерфейса, отсоединяемого с `receiver`, только для приемников событий COM, в котором *layout_dependent* параметр [event_receiver](../windows/event-receiver.md) атрибут **true**.  
  
 *источник*  
 Указатель на экземпляр источника события. В зависимости от кода `type` указано в **event_receiver**, *источника* может принимать одно из следующих действий:  
  
-   Собственный указатель на объект источника события.  
  
-   **IUnknown**-на основе указателя (источник COM).  
  
-   Указатель на управляемый объект (для управляемых событий).  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 Указатель на метод обработчика событий, который необходимо отсоединить от события. Обработчик определяется как метод класса или ссылка на этот класс, и если не указать имя класса, `__unhook` считает классом тот класс, в котором он вызван.  
  
-   События неуправляемого C++: *ReceiverClass* является классом приемника событий и `HandlerMethod` является обработчиком.  
  
-   События COM: *ReceiverClass* является интерфейсом приемника событий и `HandlerMethod` является одним из его обработчиков.  
  
-   Управляемые события: *ReceiverClass* является классом приемника событий и `HandlerMethod` является обработчиком.  
  
 `receiver` (необязательно)  
 Указатель на экземпляр класса приемника событий. Если не указать приемник, по умолчанию используется класс приемника или структура, в которой вызван `__unhook`.  
  
## <a name="usage"></a>Использование  
 Можно использовать в любой области видимости функции, включая функцию main, вне класса приемника событий.  
  
## <a name="remarks"></a>Примечания  
 С помощью встроенной функции `__unhook` в приемнике событий можно отменить привязку или отсоединить метод обработчика от метода события.  
  
 Существует три формы `__unhook`. В большинстве случаев можно использовать первую форму (четыре аргумента). Вторую форму `__unhook` (два аргумента) можно использовать только для приемника событий COM, так как с ее помощью отсоединяется весь интерфейс событий. Третья форма (один аргумент) используется для отсоединения всех делегатов от указанного источника.  
  
 Ненулевое возвращаемое значение указывает на наличие ошибки (управляемые события создадут исключение).  
  
 Вызов `__unhook` в событии и обработчике событий, которые еще не присоединены, ни к чему не приведет.  
  
 Во время компиляции компилятор проверяет, что событие существует, и выполняет проверку типа параметра с указанным обработчиком.  
  
 За исключением событий COM `__hook` и `__unhook` можно вызвать вне приемника событий.  
  
 Вместо `__unhook` можно использовать оператор -=.  
  
 Сведения о написании кода управляемых событий в новом синтаксисе см. в разделе [событие](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Класс-шаблон или структура не могут содержать события.  
  
## <a name="example"></a>Пример  
 В разделе [обработка событий в неуправляемом коде C++](../cpp/event-handling-in-native-cpp.md) и [обработка событий в COM](../cpp/event-handling-in-com.md) образцов.  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__raise](../cpp/raise.md)
