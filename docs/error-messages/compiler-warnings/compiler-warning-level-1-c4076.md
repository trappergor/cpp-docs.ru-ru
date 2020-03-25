---
title: Предупреждение компилятора (уровень 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 77efeae27a67ea844759fd9980801d3daf788e89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200269"
---
# <a name="compiler-warning-level-1-c4076"></a>Предупреждение компилятора (уровень 1) C4076

> "*Модификатор типа*": не может использоваться с типом "*TypeName*"

## <a name="remarks"></a>Remarks

Модификатор типа, который является независимо от того, является ли он **подписанным** или **неподписанным**, не может использоваться с нецелочисленным типом. *Модификатор типа* игнорируется.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4076; чтобы устранить эту проблему, удалите модификатор **неподписанного** типа:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
