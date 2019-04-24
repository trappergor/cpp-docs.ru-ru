---
title: Ошибка компилятора C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 48b378eb734c5830bedbf417d99d34955e2e6d0f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023273"
---
# <a name="compiler-error-c3551"></a>Ошибка компилятора C3551

Ожидался тип возвращаемого значения с поздним заданием

Если вы используете ключевое слово `auto` для типа возвращаемого значения функции, необходимо использовать тип возвращаемого значения с поздним заданием. В следующем примере тип возвращаемого значения с поздним заданием для функции `myFunction` является указателем на массив из четырех элементов типа `int`.

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>См. также

[auto](../../cpp/auto-cpp.md)