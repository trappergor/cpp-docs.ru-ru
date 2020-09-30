---
title: Ошибка компилятора C3138
ms.date: 11/04/2016
f1_keywords:
- C3138
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
ms.openlocfilehash: aca5c78c07852317308427d935eef5942523512b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501401"
---
# <a name="compiler-error-c3138"></a>Ошибка компилятора C3138

"Interface": интерфейс "Attribute" должен наследовать от IDispatch или от интерфейса, который наследуется от IDispatch

Интерфейс с атрибутами [Dual](../../windows/attributes/dual.md) или [DISP](../../windows/attributes/dispinterface.md) не имеет `IDispatch` прямого или косвенного базового интерфейса.

Следующий пример приводит к возникновению ошибки C3138:

```cpp
// C3138.cpp
#include <unknwn.h>

[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyCustomInterface
{
   HRESULT mf1(void);
};

[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDispInterface : IUnknown
{
   [id(1)] HRESULT mf2(void);
};

[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected
{
   HRESULT mf3(void);
};
```
