---
title: Ошибка компилятора C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: 8218233bb7a92c699952f7a506f6728386af4d17
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221072"
---
# <a name="compiler-error-c3387"></a>Ошибка компилятора C3387

"член": __declspec (dllexport)/ \_ _declspec (dllimport) не может применяться к члену типа Managed или WinRT

`dllimport` [dllexport](../../cpp/dllexport-dllimport.md) **`__declspec`** Модификаторы и не являются допустимыми для членов управляемого или среда выполнения Windowsого типа.

В следующем примере показано возникновение ошибки C3387 и приводятся сведения по ее устранению.

```cpp
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```
