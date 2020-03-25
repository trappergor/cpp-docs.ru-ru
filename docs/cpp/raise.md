---
title: __raise
ms.date: 11/04/2016
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
ms.openlocfilehash: 9238e8e3e2fcd2c2f8b6431cfb0a79d452c5adf3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179176"
---
# <a name="__raise"></a>__raise

Выделяет место вызова события.

## <a name="syntax"></a>Синтаксис

```
__raise method-declarator;
```

## <a name="remarks"></a>Remarks

Событие из управляемого кода можно вызвать только в пределах класса, где оно определено. Дополнительные сведения см. в описании [события](../extensions/event-cpp-component-extensions.md) .

Ключевое слово **__raise** вызывает ошибку при вызове события, не являющегося событием.

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

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Обработка событий](../cpp/event-handling.md)<br/>
[Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md)
