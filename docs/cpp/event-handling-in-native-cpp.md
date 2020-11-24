---
title: Обработка событий в неуправляемом C++
description: Узнайте, как использовать расширения Microsoft C++ для обработки событий C++ в собственном коде.
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: 5ad9128b7ff596674c3b08687b722c81b7a10aa8
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483182"
---
# <a name="event-handling-in-native-c"></a>Обработка событий в неуправляемом C++

При обработке событий в собственном C++ вы настраиваете источник события и приемник событий, используя атрибуты [event_source](../windows/attributes/event-source.md) и [event_receiver](../windows/attributes/event-receiver.md) соответственно, указывая `type` = `native` . Эти атрибуты позволяют классам, к которым они применяются, вызывать события и управлять событиями в собственном контексте, не являющемся контекстом COM.

> [!NOTE]
> Атрибуты событий в машинном коде C++ несовместимы со стандартным C++. Они не компилируются при указании [`/permissive-`](../build/reference/permissive-standards-conformance.md) режима соответствия.

## <a name="declaring-events"></a>Объявление событий

В классе источника событий используйте [`__event`](../cpp/event.md) ключевое слово в объявлении метода, чтобы объявить метод как событие. Обязательно объявите метод, но не определяйте его. В этом случае возникает ошибка компилятора, так как компилятор определяет метод неявно, когда он преобразуется в событие. Собственные события могут быть методами с нулевым или большим количеством параметров. Возвращаемым типом может быть **`void`** или любой целочисленный тип.

## <a name="defining-event-handlers"></a>Определение обработчиков событий

В классе приемника событий определяются обработчики событий. Обработчики событий — это методы с сигнатурами (возвращаемыми типами, соглашениями о вызовах и аргументами), которые соответствуют событию, которое они будут обработаны.

## <a name="hooking-event-handlers-to-events"></a>Подключение обработчиков событий к событиям

Кроме того, в классе приемника событий используется встроенная функция [`__hook`](../cpp/hook.md) для связывания событий с обработчиками событий и для разрыва [`__unhook`](../cpp/unhook.md) связи между событиями из обработчиков событий. Можно прикрепить несколько событий к обработчику событий либо несколько обработчиков событий к одному событию.

## <a name="firing-events"></a>События, вызывающие срабатывание

Чтобы запустить событие, вызовите метод, объявленный как событие в классе источника событий. Если обработчики прикреплены к событию, они будут вызваны.

### <a name="native-c-event-code"></a>Код события машинного кода C++

В следующем примере демонстрируется порождение события в собственном коде C++. Для компиляции и выполнения примера см. комментарии в коде. Чтобы создать код в интегрированной среде разработки Visual Studio, убедитесь, что **`/permissive-`** параметр отключен.

## <a name="example"></a>Пример

### <a name="code"></a>Код

```cpp
// evh_native.cpp
// compile by using: cl /EHsc /W3 evh_native.cpp
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
