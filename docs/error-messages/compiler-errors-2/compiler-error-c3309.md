---
title: Ошибка компилятора C3309 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3309
dev_langs:
- C++
helpviewer_keywords:
- C3309
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7d9d5f80d6c3a32f77637725e8ca53f1fdbfd51
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055485"
---
# <a name="compiler-error-c3309"></a>Ошибка компилятора C3309

"имя_макроса": в качестве имени модуля нельзя использовать макроопределение или зарезервированное слово

В качестве значения свойства имени для атрибута модуля нельзя передавать символ, который может быть расширен с помощью препроцессора. В этом случае необходимо использовать строковый литерал.

Следующий пример приводит к возникновению ошибки C3309:

```
// C3309.cpp
#define NAME MyModule
[module(name="NAME")];   // C3309
// Try the following line instead
// [module(name="MyModule")];
[coclass]
class MyClass {
public:
   void MyFunc();
};

int main() {
}
```