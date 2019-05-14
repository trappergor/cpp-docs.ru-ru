---
title: Предупреждение компилятора (уровень 1) C4581
ms.date: 11/04/2016
f1_keywords:
- C4581
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
ms.openlocfilehash: 9868d33538a1f56906455f2b1772b53eb3a7734d
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447098"
---
# <a name="compiler-warning-level-1-c4581"></a>Предупреждение компилятора (уровень 1) C4581

Рекомендуется использовать поведение: «string1» заменяется на «строка»-2 для обработки атрибута

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio 2005: проверка параметров для Visual C++ атрибуты.

В предыдущих версиях значения атрибутов были приняты ли они были заключены в кавычки. Если значение является перечислением, он должен быть не заключен в кавычки.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4581.

```
// C4581.cpp
// compile with: /c /W1
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {};

[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581
// try the following line instead
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]
class CSample : public IMyI {};
```