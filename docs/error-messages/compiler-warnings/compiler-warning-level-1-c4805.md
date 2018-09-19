---
title: Предупреждение компилятора (уровень 1) C4805 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4805
dev_langs:
- C++
helpviewer_keywords:
- C4805
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fa9352dbd4138a755c603d332ff79232d7bb72a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103455"
---
# <a name="compiler-warning-level-1-c4805"></a>Предупреждение компилятора (уровень 1) C4805

"операция": небезопасное смешение типа "тип" и типа "тип" в операции

Это предупреждение выдается для операций сравнения значений [bool](../../cpp/bool-cpp.md) и [int](../../c-language/integer-types.md). При компиляции следующего примера будет выдано предупреждение C4805:

```
// C4805.cpp
// compile with: /W1
int main() {
   int i = 1;
   bool b = true;

   if (i == b) {   // C4805, comparing bool and int variables
   }
}
```