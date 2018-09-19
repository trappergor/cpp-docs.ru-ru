---
title: Ошибка компилятора C2791 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2791
dev_langs:
- C++
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 853e9b8a7741b31a57af172427656be8a78a99f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098151"
---
# <a name="compiler-error-c2791"></a>Ошибка компилятора C2791

Недопустимое использование «Super»: «класс» не имеет базовых классов

Ключевое слово [super](../../cpp/super.md) было использовано в контексте функции-члена класса, который не имеет базовых классов.

Следующий пример приводит к возникновению ошибки C2791:

```
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```