---
title: Ошибка компилятора C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: e4661119680dff34dfaa43fb9ce71bf97150a8bd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777683"
---
# <a name="compiler-error-c3297"></a>Ошибка компилятора C3297

"ограничение_2": невозможно использовать "ограничение_1" как ограничение, поскольку "ограничение_1" имеет ограничение значения

Классы значений являются запечатанными. Если ограничение является классом значений, другое ограничение не может производиться от него.

Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C++выполняет)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3297:

```
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```