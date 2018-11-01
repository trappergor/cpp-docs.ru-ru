---
title: Предупреждение компилятора (уровень 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: 00526b3dae5035fe96ec1abb50bbdd056ceecfaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538544"
---
# <a name="compiler-warning-level-1-c4939"></a>Предупреждение компилятора (уровень 1) C4939

\#Директива #pragma vtordisp устарела и будет удален в будущих версиях Visual C++

Директива pragma [vtordisp](../../preprocessor/vtordisp.md) будет удалена в будущих выпусках Visual C++.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4939:

```
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```