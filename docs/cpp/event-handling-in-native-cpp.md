---
title: Обработка событий в неуправляемом C++
ms.date: 11/04/2016
helpviewer_keywords:
- event handling [C++], Visual C++
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
ms.openlocfilehash: 93bfcc93c680618ea3a51eabd145548a4f47563a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772336"
---
# <a name="event-handling-in-native-c"></a>Обработка событий в неуправляемом C++

В обработки собственных событий C++, как настроить событие источник и приемник событий с помощью [event_source](../windows/attributes/event-source.md) и [event_receiver](../windows/attributes/event-receiver.md) соответственно атрибуты указание `type` = `native`. Эти атрибуты позволяют классам, к которым они применены, порождать и обрабатывать события в собственном контексте, не связанном с моделью COM.

## <a name="declaring-events"></a>Объявление событий

В классе источника событий, используйте [__event](../cpp/event.md) ключевое слово в объявлении метода, чтобы объявить метод как событие. Метод должен только объявляться, но не определяться; в противном случае возникнет ошибка компилятора, поскольку компилятор определяет этот метод неявно при его преобразовании в событие. Собственные события могут быть методами с нулевым или большим количеством параметров. Тип возвращаемого значения может быть пустым или любым целочисленным типом.

## <a name="defining-event-handlers"></a>Определение обработчиков событий

В классе приемника событий необходимо указать обработчики событий, которые представляют собой методы с подписями (типы возвращаемого значения, соглашения о вызовах и аргументы), соответствующие событию, которое они будут обрабатывать.

## <a name="hooking-event-handlers-to-events"></a>Прикрепление обработчиков событий к событиям

Также в классе приемника событий, используется встроенная функция [__hook](../cpp/hook.md) для связывания событий с обработчиками событий и [__unhook](../cpp/unhook.md) Чтобы разъединить обработчики событий. Можно прикрепить несколько событий к обработчику событий либо несколько обработчиков событий к одному событию.

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