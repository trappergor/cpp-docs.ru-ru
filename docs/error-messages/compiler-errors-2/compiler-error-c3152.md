---
title: Ошибка компилятора C3152
ms.date: 11/04/2016
f1_keywords:
- C3152
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
ms.openlocfilehash: 270d2fb02365f9c2460257d96bb5f6028707553e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374889"
---
# <a name="compiler-error-c3152"></a>Ошибка компилятора C3152

construct: keyword можно применить только к классу, структуре или к виртуальной функции-члену

Определенные ключевые слова могут применяться только для класса C++.

В следующем примере показано возникновение ошибки C3152 и приводятся сведения по ее устранению.

```
// C3152.cpp
// compile with: /clr /c
ref class C {
   int (*pfn)() sealed;   // C3152
   virtual int g() sealed;   // OK
};
```
