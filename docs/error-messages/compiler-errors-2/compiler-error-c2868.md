---
title: Ошибка компилятора C2868 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2868
dev_langs:
- C++
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2de22b34f9dc564ef89d7776af86718af70d51eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037870"
---
# <a name="compiler-error-c2868"></a>Ошибка компилятора C2868

> "*идентификатор*": недопустимый синтаксис для объявления использования; требуется полное имя

Объект [объявление using](../../cpp/using-declaration.md) требует *полное имя*, оператор области действия (`::`) запятыми последовательность имен пространства имен, класса или перечисления, заканчивается имя идентификатора. Один оператор разрешения области действия может использоваться для вводят имя из глобального пространства имен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2868, а также показано правильное использование:

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```