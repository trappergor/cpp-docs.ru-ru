---
title: Ошибка компилятора C2879 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 632142ea0efd8a9d009f18b898213cfa92514b16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042480"
---
# <a name="compiler-error-c2879"></a>Ошибка компилятора C2879

«символ»: только для существующего пространства имен можно предоставить альтернативное имя, определение псевдонима пространства имен

Не удается создать [псевдоним пространства имен](../../cpp/namespaces-cpp.md#namespace_aliases) в символ, отличный от пространства имен.

Следующий пример приводит к возникновению ошибки C2879:

```
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```