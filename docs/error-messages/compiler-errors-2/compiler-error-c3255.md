---
title: Ошибка компилятора C3255 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3255
dev_langs:
- C++
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f77ad1530b59c01d36a7144e2074a4b1731a9db3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043486"
---
# <a name="compiler-error-c3255"></a>Ошибка компилятора C3255

«Тип значения»: не удается динамически выделить этот объект типа значения в собственной куче

Экземпляры типа значения (см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)), содержащие управляемые члены могут быть созданы в стеке, но не в куче.

Следующий пример приводит к возникновению ошибки C3255:

```
// C3255.cpp
// compile with: /clr
using namespace System;
value struct V {
   Object^ o;
};

value struct V2 {
   int i;
};

int main() {
   V* pv = new V;   // C3255
   V2* pv2 = new V2;
   V v2;
}
```
