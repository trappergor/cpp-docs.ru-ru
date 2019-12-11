---
title: Предупреждение компилятора (уровень 3) C4640
ms.date: 11/04/2016
f1_keywords:
- C4640
helpviewer_keywords:
- C4640
ms.assetid: f76871f6-e436-4c35-9793-d2f22f7e1c7f
ms.openlocfilehash: 00160a45e9597cfb125eaa8f50cde5fe5cfbc42d
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991874"
---
# <a name="compiler-warning-level-3-c4640"></a>Предупреждение компилятора (уровень 3) C4640

"экземпляр": Создание локального статического объекта не является потокобезопасным

Статический экземпляр объекта не является потокобезопасным.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4640:

```cpp
// C4640.cpp
// compile with: /W3
#pragma warning(default:4640)

class X {
public:
   X() {
   }
};

void f() {
   static X aX;   // C4640
}

int main() {
   f();
}
```
