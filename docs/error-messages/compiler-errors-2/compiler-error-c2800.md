---
title: Ошибка компилятора C2800 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2800
dev_langs:
- C++
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23441361ea0c8dbc241f5bf655186f0399b6b42f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016381"
---
# <a name="compiler-error-c2800"></a>Ошибка компилятора C2800

«оператор» не может быть перегружен

Следующие операторы не могут быть перегружены: доступ к члену класса (`.`), указатель на член (`.*`), разрешение области (`::`), условного выражения (`? :`), и `sizeof`.

Следующий пример приводит к возникновению ошибки C2800:

```
// C2800.cpp
// compile with: /c
class C {
   operator:: ();   // C2800
};
```