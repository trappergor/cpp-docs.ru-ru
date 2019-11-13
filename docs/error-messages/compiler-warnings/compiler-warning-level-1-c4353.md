---
title: Предупреждение компилятора (уровень 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: f04bc78e1ff6183208f888d9072bfe90b3aca083
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966548"
---
# <a name="compiler-warning-level-1-c4353"></a>Предупреждение компилятора (уровень 1) C4353

использовано нестандартное расширение: константа 0 в качестве выражения функции. Вместо этого используйте встроенную функцию "__noop"

Нельзя использовать константу нуль (0) в качестве выражения функции. Дополнительные сведения см. в разделе [__noop](../../intrinsics/noop.md).

Следующий пример приводит к возникновению ошибки C4353:

```cpp
// C4353.cpp
// compile with: /W1
void MyPrintf(void){};
#define X 0
#if X
   #define DBPRINT MyPrint
#else
   #define DBPRINT 0   // C4353 expected
#endif
int main(){
DBPRINT();
}
```