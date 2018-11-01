---
title: Предупреждение компилятора (уровень 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: 84045ea2c285be8b1c1c9d1fd62b417db00dd29c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445322"
---
# <a name="compiler-warning-level-2-c4396"></a>Предупреждение компилятора (уровень 2) C4396

"имя": если дружественное объявление ссылается на специализацию функции-шаблона, встроенный спецификатор использовать невозможно

В специализации шаблона функции нельзя указывать спецификаторы [inline](../../cpp/inline-functions-cpp.md) . В этом случае при компиляции возникает предупреждение C4396, а спецификатор inline пропускается.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите спецификатор `inline`, `__inline`или `__forceinline` из объявления дружественной функции.

## <a name="example"></a>Пример

В приведенном ниже примере показано недопустимое объявление дружественной функции со спецификатором `inline` .

```
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