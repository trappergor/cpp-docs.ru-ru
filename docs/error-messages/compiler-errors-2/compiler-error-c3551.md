---
title: Ошибка компилятора C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 1555817de6e50ea27a021718c8b094efeaebacde
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230848"
---
# <a name="compiler-error-c3551"></a>Ошибка компилятора C3551

Ожидался тип возвращаемого значения с поздним заданием

Если **`auto`** ключевое слово используется в качестве заполнителя для возвращаемого типа функции, необходимо указать тип возвращаемого значения с поздним заданным. В следующем примере тип возвращаемого значения функции с поздним заданным типом `myFunction` — это указатель на массив из четырех элементов типа **`int`** .

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>См. также статью

[auto](../../cpp/auto-cpp.md)
