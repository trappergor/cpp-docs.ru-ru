---
title: Ошибка компилятора C2178 | Документация Майкрософт
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af9efdb3258e6793a17a26b552df8ba4e63c9107
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102343"
---
# <a name="compiler-error-c2178"></a>Ошибка компилятора C2178

"*идентификатор*«не может объявляться с»*описатель*" описатель

Объект `mutable` используется спецификатор в объявлении, но описатель не допускается в данном контексте.

`mutable` Описатель могут применяться только к именам членов класса данных и не могут быть назначены имена, объявленные `const` или `static`и не могут применяться к элементам ссылки.

## <a name="example"></a>Пример

В следующем примере показано, как может возникнуть C2178 и способы ее устранения.

```
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```
