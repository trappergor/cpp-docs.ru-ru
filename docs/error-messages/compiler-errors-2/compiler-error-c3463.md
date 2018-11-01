---
title: Ошибка компилятора C3463
ms.date: 11/04/2016
f1_keywords:
- C3463
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
ms.openlocfilehash: a0c7772291085bcd872cbc1ca23b79d2fa829ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448676"
---
# <a name="compiler-error-c3463"></a>Ошибка компилятора C3463

Тип "тип" не разрешен в атрибуте implements

Недопустимый тип передан в атрибут [implements](../../windows/implements-cpp.md) . Например, можно передать в `implements`интерфейс, но нельзя передать указатель на интерфейс.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3463:

```
// C3463.cpp
// compile with: /c
#include <windows.h>
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface X {};

typedef X* PX;

[ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463
// try the following line instead
// [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ]
class CMyClass : public X {};
```