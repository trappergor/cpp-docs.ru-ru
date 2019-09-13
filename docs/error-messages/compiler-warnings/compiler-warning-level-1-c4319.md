---
title: Предупреждение компилятора (уровень 1) C4319
ms.date: 01/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 2d5ae8fcf5a527031c3a974b227f713675f31ffa
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926106"
---
# <a name="compiler-warning-level-1-c4319"></a>Предупреждение компилятора (уровень 1) C4319

> "~": нулевое расширение "*тип1*" до "*тип2*" большего размера

Результат **~** оператора (побитовое дополнение) не имеет знака и затем отсчитывается без дополнительных знаков при преобразовании в больший тип.

## <a name="example"></a>Пример

В следующем примере `~(a - 1)` выражение вычисляется как 32-разрядное длинное целое число без знака, а затем преобразуется в 64 бит на нулевое расширение. Это может привести к непредвиденному результату операции.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
