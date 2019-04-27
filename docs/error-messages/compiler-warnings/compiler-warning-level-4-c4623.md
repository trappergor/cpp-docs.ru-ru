---
title: Предупреждение компилятора (уровень 4) C4623
ms.date: 11/04/2016
f1_keywords:
- C4623
helpviewer_keywords:
- C4623
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
ms.openlocfilehash: d1b659a6aed593a2e3f01ac1b82e60878cb09c80
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220472"
---
# <a name="compiler-warning-level-4-c4623"></a>Предупреждение компилятора (уровень 4) C4623

"`derived class`": не удалось создать конструктор по умолчанию, так как конструктор по умолчанию для базового класса недоступен или удален

Конструктор базового класса недоступен и не был создан для производного класса. Любая попытка создать объект этого типа в стеке приведет к ошибке компилятора.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4623.

```
// C4623.cpp
// compile with: /W4
#pragma warning(default : 4623)
class B {
   B();
};

class C {
public:
   C();
};

class D : public B {};   // C4623 - to fix, make B's constructor public
class E : public C {};   // OK - class C constructor is public

int main() {
   // D d;  will cause an error
}
```