---
title: Ошибка компилятора C2516
ms.date: 11/04/2016
f1_keywords:
- C2516
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
ms.openlocfilehash: 678c90c5f4d41b0a05bbb07f2aada82e9bfcdb1e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214663"
---
# <a name="compiler-error-c2516"></a>Ошибка компилятора C2516

"имя": не является допустимым базовым классом

Класс является производным от имени типа, определенного **`typedef`** инструкцией.

Следующий пример приводит к возникновению ошибки C2516:

```cpp
// C2516.cpp
typedef unsigned long ulong;
class C : public ulong {}; // C2516
```
