---
title: Ошибка компилятора C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: 9e24fc28f84bfacb7478d700047c4eb1363247de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451276"
---
# <a name="compiler-error-c3246"></a>Ошибка компилятора C3246

"класс": не может наследовать от типа "тип", так как он был объявлен как sealed

Класс, помеченный как [sealed](../../windows/sealed-cpp-component-extensions.md) , не может быть базовым классом для каких-либо других классов.

В следующем примере возникает ошибка C3246:

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
