---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: 3a8dce21aa707a1a52c647c9efee5ab806511ca8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454565"
---
# <a name="noinline"></a>noinline

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

**__declspec(noinline)** указывает компилятору не функция-член (функция в классе).

Запрещать использовать функцию как встроенную имеет смысл, если она небольшая и не оказывает критического влияния на производительность кода. То есть, если функция небольшая и вряд ли будет вызываться часто (например, функция, которая обрабатывает условие ошибки).

Имейте в виду, что если функция отмечена **noinline**, вызывающая функция будет уменьшается и она сама является кандидатом для встраивания компилятором.

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)

