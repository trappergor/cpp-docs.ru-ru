---
title: Ошибка компилятора C2267 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2267
dev_langs:
- C++
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 080f6ebfda8dbdaa1f0bf70faa3b6d5c7545d66e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035270"
---
# <a name="compiler-error-c2267"></a>Ошибка компилятора C2267

«функция»: статические функции с областью видимости блока недопустимы

Локальная функция объявлена `static`. Статические функции должны иметь глобальной области.

Следующий пример приводит к возникновению ошибки C2267:

```
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```