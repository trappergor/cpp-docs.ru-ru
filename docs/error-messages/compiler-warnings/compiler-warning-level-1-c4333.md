---
title: Предупреждение компилятора (уровень 1) C4333
ms.date: 11/04/2016
f1_keywords:
- C4333
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
ms.openlocfilehash: 534491db2d612f251a6fd85c9239537569083874
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162937"
---
# <a name="compiler-warning-level-1-c4333"></a>Предупреждение компилятора (уровень 1) C4333

"оператор": слишком большое смещение вправо, потери данных

Операция сдвига вправо слишком велика.  Все значащие биты сдвигаются, и результат всегда будет равен нулю.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4333.

```cpp
// C4333.cpp
// compile with: /c /W1
unsigned shift8 (unsigned char c) {
   return c >> 8;   // C4333

   // try the following line instead
   // return c >> 4;   // OK
}
```
