---
title: __raise
description: Узнайте, как использовать ключевое слово расширения Microsoft C++ `__raise` для обработки собственных событий.
ms.date: 11/20/2020
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.openlocfilehash: c9df602803062bc51b8c0cee13f17263cdc91786
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483154"
---
# <a name="__raise-keyword"></a>`__raise` This

Выделяет место вызова события.

> [!NOTE]
> Атрибуты событий в машинном коде C++ несовместимы со стандартным C++. Они не компилируются при указании [`/permissive-`](../build/reference/permissive-standards-conformance.md) режима соответствия.

## <a name="syntax"></a>Синтаксис

> **`__raise`** *`method-declarator`* **`;`**

## <a name="remarks"></a>Комментарии

Из управляемого кода событие может быть вызвано только из класса, в котором он определен. Дополнительные сведения см. в разделе [`event`](../extensions/event-cpp-component-extensions.md).

Ключевое слово **`__raise`** вызывает ошибку при вызове события, не являющегося событием.

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

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

[Словами](../cpp/keywords-cpp.md)\
[Обработка событий](../cpp/event-handling.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[Расширения компонентов для .NET и UWP](../extensions/component-extensions-for-runtime-platforms.md)
