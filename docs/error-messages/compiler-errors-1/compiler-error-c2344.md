---
title: Ошибка компилятора C2344
ms.date: 11/04/2016
f1_keywords:
- C2344
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
ms.openlocfilehash: d1ba3a0f975dbc96c9c6ca51a8dac89b5a614572
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439486"
---
# <a name="compiler-error-c2344"></a>Ошибка компилятора C2344

align(#): выравнивание должно быть степенью двух

При использовании ключевого слова [align](../../cpp/align-cpp.md) передаваемое значение должно быть степенью двух.

Например, приведенный ниже код вызывает ошибку C2344, так как число 3 не является степенью двух.

```
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```