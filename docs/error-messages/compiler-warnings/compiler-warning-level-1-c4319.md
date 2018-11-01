---
title: Предупреждение компилятора (уровень 1) C4319
ms.date: 1/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 20b268bacd6e7e259e9b4fa1c9e98fa6fd353718
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599450"
---
# <a name="compiler-warning-level-1-c4319"></a>Предупреждение компилятора (уровень 1) C4319

> "~": ноль расширение "*тип1*«to»*тип2*" большего размера

Результат **~** оператор (побитовое дополнение) не имеет знака и затем использует нулевое расширение при преобразовании к большему типу.

## <a name="example"></a>Пример

В следующем примере `~(a - 1)` вычисляется как 32-разрядное выражение long без знака и затем преобразуется в 64 бита, с помощью нулевого расширения. Это может привести к непредвиденному результату операции.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
