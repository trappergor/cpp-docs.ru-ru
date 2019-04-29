---
title: Ошибка компилятора C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 9ac8f5e5edb1a6ed7314c5b5d125fcc9bfbe67de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378925"
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