---
title: Предупреждение компилятора (уровень 1) C4096
ms.date: 11/04/2016
f1_keywords:
- C4096
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
ms.openlocfilehash: 8f526b26eda4c02825d225aa007c6029cc4b03dd
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627075"
---
# <a name="compiler-warning-level-1-c4096"></a>Предупреждение компилятора (уровень 1) C4096

"a": интерфейс не является COM-интерфейсом; не будет выдаваться в IDL

Определение интерфейса, которое может быть предназначено в качестве COM-интерфейса, не было определено как COM-интерфейс, и поэтому не будет выдаваться в файл IDL.

Атрибуты списка, указывающие, что интерфейс является COM-интерфейсом, см. в разделе [атрибуты интерфейса](../../windows/attributes/interface-attributes.md) .

Следующий пример приводит к возникновению ошибки C4096:

```cpp
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```