---
title: Предупреждение компилятора (уровень 2) C4396 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4396
dev_langs:
- C++
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa0a084e90db9d48f517bfe65c6340eb532f0ae6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118574"
---
# <a name="compiler-warning-level-2-c4396"></a>Предупреждение компилятора (уровень 2) C4396

"имя": если дружественное объявление ссылается на специализацию функции-шаблона, встроенный спецификатор использовать невозможно

В специализации шаблона функции нельзя указывать любой из [встроенного](../../cpp/inline-functions-cpp.md) спецификаторы. В этом случае при компиляции возникает предупреждение C4396, а спецификатор inline пропускается.

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