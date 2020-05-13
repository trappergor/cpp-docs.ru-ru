---
title: Обработка событий в неуправляемом C++
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
ms.openlocfilehash: cc9265cd3f9f400e2880405019e4d2c9a934f10a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180086"
---
# <a name="event-handling-in-native-c"></a>Обработка событий в неуправляемом C++

При обработке C++ собственных событий вы настраиваете источник события и приемник событий, используя атрибуты [event_source](../windows/attributes/event-source.md) и [event_receiver](../windows/attributes/event-receiver.md) соответственно, указывая `type`=`native`. Эти атрибуты позволяют классам, к которым они применены, порождать и обрабатывать события в собственном контексте, не связанном с моделью COM.

## <a name="declaring-events"></a>Объявление событий

В классе источника событий используйте ключевое слово [__event](../cpp/event.md) в объявлении метода, чтобы объявить метод как событие. Метод должен только объявляться, но не определяться; в противном случае возникнет ошибка компилятора, поскольку компилятор определяет этот метод неявно при его преобразовании в событие. Собственные события могут быть методами с нулевым или большим количеством параметров. Тип возвращаемого значения может быть пустым или любым целочисленным типом.

## <a name="defining-event-handlers"></a>Определение обработчиков событий

В классе приемника событий необходимо указать обработчики событий, которые представляют собой методы с подписями (типы возвращаемого значения, соглашения о вызовах и аргументы), соответствующие событию, которое они будут обрабатывать.

## <a name="hooking-event-handlers-to-events"></a>Прикрепление обработчиков событий к событиям

Кроме того, в классе приемника событий можно использовать встроенную функцию [__hook](../cpp/hook.md) , чтобы связать события с обработчиками событий и [__unhook](../cpp/unhook.md) , чтобы отсоединить события от обработчиков событий. Можно прикрепить несколько событий к обработчику событий либо несколько обработчиков событий к одному событию.

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

### <a name="output"></a>Выходные данные

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>См. также раздел

[Обработка событий](../cpp/event-handling.md)
