---
title: Предупреждение компилятора (уровень 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d14a1902db4dcf2224ce6a58db120a81ebb5620f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327357"
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