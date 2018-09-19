---
title: Ошибка компилятора C2459 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2459
dev_langs:
- C++
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b67c5ba4c714b096da58b1e4d837840dc6b5fd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113218"
---
# <a name="compiler-error-c2459"></a>Ошибка компилятора C2459

«Идентификатор»: определяется; не удается добавить в качестве анонимного члена

Класс, структура или объединение переопределяется в его области член анонимного объединения.

Следующий пример приводит к возникновению ошибки C2459:

```
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```