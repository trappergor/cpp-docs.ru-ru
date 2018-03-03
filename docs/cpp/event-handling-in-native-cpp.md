---
title: "Обработка событий в машинном коде C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling [C++], Visual C++
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 157b31f244ce5400aac5857f2473deb67938d8d0
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="event-handling-in-native-c"></a>Обработка событий в неуправляемом C++

В машинном коде C++ при обработке событий настраиваются событий источник и приемник событий с помощью [event_source](../windows/event-source.md) и [event_receiver](../windows/event-receiver.md) атрибуты, соответственно, указав `type` = `native`. Эти атрибуты позволяют классам, к которым они применены, порождать и обрабатывать события в собственном контексте, не связанном с моделью COM.

## <a name="declaring-events"></a>Объявление событий

В классе источника событий используйте [__event](../cpp/event.md) ключевое слово в объявлении метода, чтобы объявить метод как событие. Метод должен только объявляться, но не определяться; в противном случае возникнет ошибка компилятора, поскольку компилятор определяет этот метод неявно при его преобразовании в событие. Собственные события могут быть методами с нулевым или большим количеством параметров. Тип возвращаемого значения может быть пустым или любым целочисленным типом.  
  
## <a name="defining-event-handlers"></a>Определение обработчиков событий

В классе приемника событий необходимо указать обработчики событий, которые представляют собой методы с подписями (типы возвращаемого значения, соглашения о вызовах и аргументы), соответствующие событию, которое они будут обрабатывать.  
  
## <a name="hooking-event-handlers-to-events"></a>Прикрепление обработчиков событий к событиям  

Также в классе приемника событий, можно использовать встроенную функцию [__hook](../cpp/hook.md) для связывания событий с обработчиками событий и [__unhook](../cpp/unhook.md) отменить связь событий от обработчиков событий. Можно прикрепить несколько событий к обработчику событий либо несколько обработчиков событий к одному событию.  
  
## <a name="firing-events"></a>Запуск событий  

Для порождения события просто вызовите метод, объявленный как событие в классе источника события. Если обработчики прикреплены к событию, они будут вызваны.  
  
### <a name="native-c-event-code"></a>Код собственного события C++  

В следующем примере демонстрируется порождение события в собственном коде C++. Для компиляции и выполнения примера см. комментарии в коде.  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```cpp  
// evh_native.cpp  
#include <stdio.h>  
  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
  
[event_receiver(native)]  
class CReceiver {  
public:  
   void MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
   }  
  
   void MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
   }  
  
   void hookEvent(CSource* pSource) {  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void unhookEvent(CSource* pSource) {  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   CSource source;  
   CReceiver receiver;  
  
   receiver.hookEvent(&source);  
   __raise source.MyEvent(123);  
   receiver.unhookEvent(&source);  
}  
```  
  
### <a name="output"></a>Вывод  
  
```Output
MyHandler2 was called with value 123.  
MyHandler1 was called with value 123.  
```  
  
## <a name="see-also"></a>См. также

[Обработка событий](../cpp/event-handling.md)  

