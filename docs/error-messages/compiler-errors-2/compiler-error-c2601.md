---
title: Ошибка компилятора C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: f18819e5f078cb85121160af1d4a3fc24a365a68
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615196"
---
# <a name="compiler-error-c2601"></a>Ошибка компилятора C2601

«функция»: недопустимые локальные определения функций

Код пытается определить функцию внутри функции.

Или могут существовать дополнительные скобки в исходном коде, перед расположением C2601 ошибки.

Следующий пример приводит к возникновению ошибки C2601:

```
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```