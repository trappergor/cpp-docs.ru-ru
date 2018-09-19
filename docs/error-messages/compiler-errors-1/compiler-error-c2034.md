---
title: Ошибка компилятора C2034 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2034
dev_langs:
- C++
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1dadc3249b7e58410eb153f8d298fca06a44ea7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034425"
---
# <a name="compiler-error-c2034"></a>Ошибка компилятора C2034

«Идентификатор»: тип битового поля слишком мал для заданного числа битов

Количество битов в объявлении битового поля превышает размер базового типа.

Следующий пример приводит к возникновению ошибки C2034:

```
// C2034.cpp
struct A {
   char test : 9;   // C2034, char has 8 bits
};
```

Возможное решение

```
// C2034b.cpp
// compile with: /c
struct A {
   char test : 8;
};
```