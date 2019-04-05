---
title: Ошибка компилятора C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: eb5ba268508922daf00adb49cf611c038db76343
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776705"
---
# <a name="compiler-error-c3246"></a>Ошибка компилятора C3246

"класс": не может наследовать от типа "тип", так как он был объявлен как sealed

Класс, помеченный как [sealed](../../extensions/sealed-cpp-component-extensions.md) , не может быть базовым классом для каких-либо других классов.

В следующем примере возникает ошибка C3246:

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
