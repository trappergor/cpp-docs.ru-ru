---
title: Предупреждение компилятора (уровень 3) C4334 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7bb16ea38b2c2112c12c561398341a7d1adbfc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044019"
---
# <a name="compiler-warning-level-3-c4334"></a>Предупреждение компилятора (уровень 3) C4334

«operator»: результат 32-разрядного смещения неявно преобразуется в 64 бита (был 64-разрядное смещение?)

Результат 32-разрядного смещения неявно преобразовано в 64-разрядной и компилятор предполагает, что действительно был 64-разрядное смещение.  Чтобы устранить это предупреждение, используйте 64-разрядное смещение или явно привести результат сдвига на 64-разрядную версию.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4334.

```
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```