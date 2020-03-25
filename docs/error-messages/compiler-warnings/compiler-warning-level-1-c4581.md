---
title: Предупреждение компилятора (уровень 1) C4581
ms.date: 11/04/2016
f1_keywords:
- C4581
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
ms.openlocfilehash: 491121bc236c54ce5b74c76abfa6a650ff7a99ff
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162170"
---
# <a name="compiler-warning-level-1-c4581"></a>Предупреждение компилятора (уровень 1) C4581

нерекомендуемое поведение: "строка Строка1" заменена на "строка2" для обработки атрибута

Эта ошибка может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio 2005: Проверка параметров для визуальных C++ атрибутов.

В предыдущих версиях значения атрибутов были приняты независимо от того, были ли они заключены в кавычки. Если значение является перечислением, оно не должно заключаться в кавычки.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4581.

```cpp
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
