---
title: Ошибка компилятора C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: 79a5bc77f0e18a8e55954e25e67a836af8157596
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755139"
---
# <a name="compiler-error-c3209"></a>Ошибка компилятора C3209

"класс": универсальный класс должен быть управляемым или Винрткласс

Универсальный класс должен быть управляемым классом или классом среды выполнения Windows.

В следующем примере показано возникновение ошибки C3209 и приводятся сведения по ее устранению.

```cpp
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```
