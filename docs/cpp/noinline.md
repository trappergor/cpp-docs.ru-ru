---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: 6e424846c46dd50852b62008c4f1f38827da849c
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857415"
---
# <a name="noinline"></a>noinline

**Блок, относящийся только к системам Майкрософт**

**__declspec (noinline)** указывает компилятору никогда не подставляемую конкретную функцию-член (функцию в классе).

Запрещать использовать функцию как встроенную имеет смысл, если она небольшая и не оказывает критического влияния на производительность кода. То есть, если функция небольшая и вряд ли будет вызываться часто (например, функция, которая обрабатывает условие ошибки).

Помните, что если функция помечена как **noinline**, то вызывающая функция будет меньше и, таким же, является кандидатом для встраивания компилятора.

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)
