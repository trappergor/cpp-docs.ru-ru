---
title: Ошибка компилятора C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: 1344bd8bde532d2e813ca03e173b995e935c76b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243765"
---
# <a name="compiler-error-c2569"></a>Ошибка компилятора C2569

«EnumOrUnion»: перечисление или объединение не может использоваться в качестве базового класса

Если тип должен быть производным от указанного объединения или перечисления, измените объединения или перечисления класса или структуры.

Следующий пример приводит к возникновению ошибки C2569:

```
// C2569.cpp
// compile with: /c
union ubase {};
class cHasPubUBase : public ubase {};   // C2569
// OK
struct sbase {};
class cHasPubUBase : public sbase {};
```