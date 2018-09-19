---
title: Ошибка компилятора C2351 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2351
dev_langs:
- C++
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c92f955beaafa92a8259df4878301158d03c18ff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034776"
---
# <a name="compiler-error-c2351"></a>Ошибка компилятора C2351

устаревший синтаксис инициализации конструктора C++

В списке инициализации нового стиля для конструктора необходимо явно задать имена каждой прямой базовый класс, даже если это только базовый класс.

В следующем примере возникает в C2351:

```
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```