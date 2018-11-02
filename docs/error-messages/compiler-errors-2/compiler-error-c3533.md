---
title: Ошибка компилятора C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 59ceea942d9165f6f7c6161032e96404bc0dcba7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547255"
---
# <a name="compiler-error-c3533"></a>Ошибка компилятора C3533

«Тип»: параметр не может иметь тип, содержащий «auto»

Параметр метода или шаблона не могут объявляться с `auto` ключевое слово Если значение по умолчанию [/Zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) параметр компилятора.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Удалить `auto` ключевое слово из объявления параметра.

## <a name="example"></a>Пример

Следующий пример вызывает C3533, так как он объявляет параметр функции с `auto` ключевое слово и она компилируется с **/Zc: auto**.

```
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

## <a name="example"></a>Пример

Следующий пример вызывает C3533 в режим C ++ 14, так как он объявляет параметр шаблона с `auto` ключевое слово и она компилируется с **/Zc: auto**. (В C ++ 17, это допустимое определение шаблона класса с параметром отдельный шаблон не являющийся типом, тип которой выводится.)

```
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)
