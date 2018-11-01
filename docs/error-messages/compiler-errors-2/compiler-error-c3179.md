---
title: Ошибка компилятора C3179
ms.date: 11/04/2016
f1_keywords:
- C3179
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
ms.openlocfilehash: a5c92e8a776e318e732448ba31beedef946d9f41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511611"
---
# <a name="compiler-error-c3179"></a>Ошибка компилятора C3179

неименованный управляемый тип или тип WinRT не допускается

Все классы и структуры среды CLR и WinRT должны иметь имена.

В следующем примере показано возникновение ошибки C3179 и приводятся сведения по ее устранению.

```
// C3179a.cpp
// compile with: /clr /c
typedef value struct { // C3179
// try the following line instead
// typedef value struct MyStruct {
   int i;
} V;
```
