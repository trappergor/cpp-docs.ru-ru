---
title: Предупреждение (уровень 1) C4319 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1b5fe896ae7d8f43708b60ee4dda486ef08f428
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284749"
---
# <a name="compiler-warning-level-1-c4319"></a>Предупреждение компилятора (уровень 1) C4319

> "~": нулевое расширение "*тип1*«to»*тип2*" большего размера

Результат **~** (побитовое дополнение) не имеет знака и затем использует нулевое расширение при преобразовании к большему типу.

## <a name="example"></a>Пример

В следующем примере `~(a - 1)` вычисляется как 32-разрядное выражение long без знака и затем преобразуется в 64-разрядная с помощью нулевого расширения. Это может привести к непредвиденному результату операции.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
