---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: bedf17072c06ec893b9cbd83b46403dcd3bc1560
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186689"
---
# <a name="noinline"></a>noinline

**Блок, относящийся только к системам Microsoft**

**`__declspec(noinline)`** Указывает компилятору никогда не подставляемую конкретную функцию-член (функцию в классе).

Запрещать использовать функцию как встроенную имеет смысл, если она небольшая и не оказывает критического влияния на производительность кода. То есть, если функция небольшая и вряд ли будет вызываться часто (например, функция, которая обрабатывает условие ошибки).

Помните, что если функция помечена **`noinline`** , то вызывающая функция будет меньше и, таким же, является кандидатом для встраивания компилятора.

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
