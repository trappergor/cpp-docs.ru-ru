---
title: Ошибка компилятора C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: ce95bba417e9be3603f15376a0fd65a48f951a2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755646"
---
# <a name="compiler-error-c3533"></a>Ошибка компилятора C3533

"тип": параметр не может иметь тип, содержащий "Auto"

Метод или параметр шаблона не может быть объявлен с ключевым словом `auto`, если действует параметр компилятора [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) по умолчанию.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Удалите ключевое слово `auto` из объявления параметра.

## <a name="example"></a>Пример

Следующий пример возвращает C3533, так как объявляет параметр функции с ключевым словом `auto` и компилируется с помощью параметра **/Zc: Auto**.

```cpp
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

## <a name="example"></a>Пример

В следующем примере демонстрируется C3533 в режиме C++ 14, так как он объявляет параметр шаблона с ключевым словом `auto` и компилируется с помощью параметра **/Zc: Auto**. (В C++ 17 это допустимое определение шаблона класса с одним нетипизированным параметром шаблона, тип которого выведен.)

```cpp
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>См. также:

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)
