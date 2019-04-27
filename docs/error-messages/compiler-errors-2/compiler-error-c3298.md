---
title: Ошибка компилятора C3298
ms.date: 11/04/2016
f1_keywords:
- C3298
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
ms.openlocfilehash: fe6913d402c6ce4df3551c159eb56a12590799cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222535"
---
# <a name="compiler-error-c3298"></a>Ошибка компилятора C3298

"ограничение_1": невозможно использовать "ограничение_2" как ограничение, поскольку "ограничение_2" имеет ограничение ссылки, а "ограничение_1" имеет ограничение значения

Нельзя указывать взаимно исключающие характеристики для ограничения. Например, параметр универсального типа не может быть ограничен одновременно типом значения и ссылочным типом.

Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C++выполняет)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3298.

```
// C3298.cpp
// compile with: /clr /c
generic<class T, class U>
where T : ref class
where U : T, value class   // C3298
public ref struct R {};
```