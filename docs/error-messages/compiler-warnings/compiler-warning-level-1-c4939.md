---
title: Предупреждение компилятора (уровень 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: 5c87dad744281464599ee6c28b5bcf6e350b9feb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199281"
---
# <a name="compiler-warning-level-1-c4939"></a>Предупреждение компилятора (уровень 1) C4939

Директива pragma \#vtordisp устарела и будет удалена в следующем выпуске VisualC++

Директива pragma [vtordisp](../../preprocessor/vtordisp.md) будет удалена в будущих выпусках Visual C++.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4939:

```cpp
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```
