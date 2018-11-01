---
title: lock::operator!=
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
helpviewer_keywords:
- lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
ms.openlocfilehash: 5f202d6e7cc4c023b366f370ec2c419336822964
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558448"
---
# <a name="lockoperator"></a>lock::operator!=

Оператор неравенства.

## <a name="syntax"></a>Синтаксис

```
template<class T> bool operator!=(
   T t
);
```

#### <a name="parameters"></a>Параметры

*t*<br/>
Объект для сравнения на предмет их неравенства.

## <a name="return-value"></a>Возвращаемое значение

Возвращает **true** Если `t` отличается от объект блокировки, **false** в противном случае.

## <a name="example"></a>Пример

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\lock.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[Члены lock](../dotnet/lock-members.md)<br/>
[lock::operator==](../dotnet/lock-operator-equality.md)