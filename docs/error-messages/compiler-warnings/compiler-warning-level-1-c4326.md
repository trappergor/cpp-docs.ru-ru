---
title: Предупреждение компилятора (уровень 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d14a1902db4dcf2224ce6a58db120a81ebb5620f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601166"
---
# <a name="compiler-warning-level-1-c4326"></a>Предупреждение компилятора (уровень 1) C4326

> Тип возвращаемого значения "*функция*«должно быть»*тип1*«вместо of»*тип2*"

## <a name="remarks"></a>Примечания

Функция возвращает тип, отличное от *тип1*. Например, с помощью [/Za](../../build/reference/za-ze-disable-language-extensions.md), **основной** не возвратил **int**.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4326 и показаны способы ее устранения:

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```