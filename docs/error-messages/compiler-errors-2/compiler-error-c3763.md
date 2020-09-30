---
title: Ошибка компилятора C3763
ms.date: 11/04/2016
f1_keywords:
- C3763
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
ms.openlocfilehash: 7ccb3d846982bbf9a52a7267549f6481b5a1bd9b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503958"
---
# <a name="compiler-error-c3763"></a>Ошибка компилятора C3763

"тип": "retval" и "out" могут использоваться только в типе указателя данных

Атрибуты [out](../../windows/attributes/out-cpp.md) и [retval](../../windows/attributes/retval.md) могут присутствовать только в параметрах типа pointer. Удалите атрибут или установите параметр указателя типа.

Следующий пример приводит к возникновению ошибки C3763:

```cpp
// C3763.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlplus.h>
#include <atlcom.h>

[ module(name=test) ];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IF84 : IDispatch
{
   [id(0x00000002)]HRESULT m2([out]unsigned char);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class CF84 : public IF84
{   // C3763
public:
   HRESULT __stdcall m2(unsigned char i)
   {
      return S_OK;
   }
};

int main()
{
}
```
