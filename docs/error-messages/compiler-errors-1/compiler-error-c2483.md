---
title: Ошибка компилятора C2483 | Документация Майкрософт
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2483
dev_langs:
- C++
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be2a2caef9e1252bf1ab36253a7f5f715b94d5a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031617"
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