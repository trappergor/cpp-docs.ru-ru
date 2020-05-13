---
title: Предупреждение компилятора (уровень 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: 32bcd85b1cd1bb6c89678daae02f4f31a9318b6d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162976"
---
# <a name="compiler-warning-level-1-c4326"></a>Предупреждение компилятора (уровень 1) C4326

> возвращаемый тип "*функция*" должен быть "*тип1*", а не "*тип2*"

## <a name="remarks"></a>Remarks

Функция вернула тип, отличный от *Type1*. Например, при использовании [/Za](../../build/reference/za-ze-disable-language-extensions.md)значения/ZA **Main** не возвращает **целое**число.

## <a name="example"></a>Пример

В следующем примере создается C4326 и демонстрируется его устранение.

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```
