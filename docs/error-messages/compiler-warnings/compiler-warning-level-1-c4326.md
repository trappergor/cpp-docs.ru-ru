---
title: Предупреждение компилятора (уровень 1) C4326 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4326
dev_langs:
- C++
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cee18a9ccc807370cf2fb40748939f211a4ba52f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211008"
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