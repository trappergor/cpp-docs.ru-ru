---
title: Предупреждение компилятора (уровень 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: f37fcc7ece09bb9028a522ec6baf85d0e0e585c2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161819"
---
# <a name="compiler-warning-level-2-c4396"></a>Предупреждение компилятора (уровень 2) C4396

"имя": если дружественное объявление ссылается на специализацию функции-шаблона, встроенный спецификатор использовать невозможно

В специализации шаблона функции нельзя указывать спецификаторы [inline](../../cpp/inline-functions-cpp.md) . В этом случае при компиляции возникает предупреждение C4396, а спецификатор inline пропускается.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите спецификатор `inline`, `__inline`или `__forceinline` из объявления дружественной функции.

## <a name="example"></a>Пример

В приведенном ниже примере показано недопустимое объявление дружественной функции со спецификатором `inline` .

```cpp
// C4396.cpp
// compile with: /W2 /c

class X;
template<class T> void Func(T t, int i);

class X {
    friend inline void Func<char>(char t, int i);  //C4396
// try the following line instead
//    friend void Func<char>(char t, int i);
    int i;
};
```
