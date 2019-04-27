---
title: Ошибка компилятора C2147
ms.date: 11/04/2016
f1_keywords:
- C2147
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
ms.openlocfilehash: 0a093bbbaf9cf9f72625226f949a27b681005c35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175398"
---
# <a name="compiler-error-c2147"></a>Ошибка компилятора C2147

Синтаксическая ошибка: «идентификатор» — это новое ключевое слово

Использовался идентификатор, который теперь является зарезервированным словом в языке.

Следующий пример приводит к возникновению ошибки C2147:

```
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```