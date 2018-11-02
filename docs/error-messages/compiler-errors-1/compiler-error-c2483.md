---
title: Ошибка компилятора C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: d1a5632328c00ca2dcd03519d03fbdb648776a51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637883"
---
# <a name="compiler-error-c2483"></a>Ошибка компилятора C2483

>"*идентификатор*": объект с конструктором или деструктором не могут объявляться как «thread»

Это сообщение об ошибке является устаревшим в Visual Studio 2015 и более поздних версий. В предыдущих версиях, переменных, объявленных с `thread` атрибут нельзя инициализировать с конструктором или другим выражением, которое требуется вычисление во время выполнения. Статическое выражение необходим для инициализации `thread` данных.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2483 в Visual Studio 2013 и более ранних версий.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>См. также

[thread](../../cpp/thread.md)