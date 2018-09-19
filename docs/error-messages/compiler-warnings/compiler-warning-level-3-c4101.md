---
title: Предупреждение (уровень 3) C4101 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1549a327329d438cb30bd6908e07419eb1b6bc1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060841"
---
# <a name="compiler-warning-level-3-c4101"></a>Компилятор предупреждение (уровень 3) C4101

«Идентификатор»: неиспользованная локальная переменная

Локальной переменной никогда не используется. Это предупреждение может возникнуть в ситуации, когда очевидно:

```
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Однако, это предупреждение также может возникнуть при вызове **статический** функция-член через экземпляр класса:

```
// C4101b.cpp
// compile with:  /W3
struct S {
   static int func()
   {
      return 1;
   }
};

int main() {
   S si;   // C4101, si is never used
   int y = si.func();
   return y;
}
```

В этом случае компилятор использует сведения о `si` для доступа к **статический** функция, а экземпляр класса не требуется для вызова **статический** функции; таким образом предупреждение. Чтобы устранить это предупреждение, можно выполнить следующее.

- Добавьте конструктор, в котором компилятор будет использовать экземпляр `si` в вызове `func`.

- Удалить **статический** ключевое слово из определения `func`.

- Вызовите **статический** функции явно: `int y = S::func();`.