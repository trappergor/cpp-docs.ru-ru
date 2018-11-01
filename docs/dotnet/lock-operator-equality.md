---
title: lock::operator==
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
helpviewer_keywords:
- lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
ms.openlocfilehash: 2e7e78f5d03074058dadd969f150855f305cf85e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647870"
---
# <a name="lockoperator"></a>lock::operator==

Оператор равенства.

## <a name="syntax"></a>Синтаксис

```
template<class T> bool operator==(
   T t
);
```

#### <a name="parameters"></a>Параметры

*t*<br/>
Объект для сравнения на равенство.

## <a name="return-value"></a>Возвращаемое значение

Возвращает **true** Если `t` совпадает со значением объект блокировки, **false** в противном случае.

## <a name="example"></a>Пример

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\lock.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[Члены lock](../dotnet/lock-members.md)<br/>
[lock::operator!=](../dotnet/lock-operator-inequality.md)