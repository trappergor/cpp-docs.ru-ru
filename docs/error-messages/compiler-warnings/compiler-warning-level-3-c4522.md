---
title: Предупреждение компилятора (уровень 3) C4522 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4522
dev_langs:
- C++
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65662d3e62abbeb06127c7b5a49479a23fb20a7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070942"
---
# <a name="compiler-warning-level-3-c4522"></a>Предупреждение компилятора (уровень 3) C4522

«класс»: заданы несколько операторов присваивания

Этот класс содержит несколько операторов присваивания одного типа. Это сообщение является информационным; конструкторы можно вызвать в приложении.

Используйте [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить это предупреждение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4522.

```
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```