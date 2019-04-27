---
title: __raise
ms.date: 11/04/2016
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
ms.openlocfilehash: c5703c87945667f4ac65647019a72b304363bee2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244508"
---
# <a name="raise"></a>__raise

Выделяет место вызова события.

## <a name="syntax"></a>Синтаксис

```
__raise method-declarator;
```

## <a name="remarks"></a>Примечания

Событие из управляемого кода можно вызвать только в пределах класса, где оно определено. См. в разделе [событий](../extensions/event-cpp-component-extensions.md) Дополнительные сведения.

Ключевое слово **__raise** вызывает ошибку, которая возникает при вызове непредвиденных событий.

> [!NOTE]
>  Класс-шаблон или структура не могут содержать события.

## <a name="example"></a>Пример

```cpp
// EventHandlingRef_raise.cpp
struct E {
   __event void func1();
   void func1(int) {}

   void func2() {}

   void b() {
      __raise func1();
      __raise func1(1);  // C3745: 'int Event::bar(int)':
                         // only an event can be 'raised'
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func1();
   __raise e.func1(1);  // C3745
   __raise e.func2();   // C3745
}
```

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Обработка событий](../cpp/event-handling.md)<br/>
[Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md)