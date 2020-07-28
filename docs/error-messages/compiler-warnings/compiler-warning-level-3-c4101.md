---
title: Предупреждение компилятора (уровень 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: f9d3875fdc17def1e7d3bcb72149c5faf90f656a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220058"
---
# <a name="compiler-warning-level-3-c4101"></a>Предупреждение компилятора (уровень 3) C4101

"идентификатор": локальная переменная без ссылки

Локальная переменная никогда не используется. Это предупреждение появляется в очевидной ситуации:

```cpp
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Однако это предупреждение также возникает при вызове функции- **`static`** члена через экземпляр класса:

```cpp
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

В этом случае компилятор использует сведения о `si` доступе к **`static`** функции, но экземпляр класса не требуется для вызова **`static`** функции. Следовательно, это предупреждение. Чтобы устранить это предупреждение, можно выполнить следующие действия.

- Добавьте конструктор, в котором компилятор будет использовать экземпляр `si` в вызове `func` .

- Удалите **`static`** ключевое слово из определения `func` .

- Вызовите **`static`** функцию явным образом: `int y = S::func();` .
