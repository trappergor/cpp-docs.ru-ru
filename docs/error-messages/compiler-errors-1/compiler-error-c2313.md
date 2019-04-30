---
title: Ошибка компилятора C2313
ms.date: 11/04/2016
f1_keywords:
- C2313
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
ms.openlocfilehash: 276dea87770035967a08ca5ac3e95316832ffc1b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344888"
---
# <a name="compiler-error-c2313"></a>Ошибка компилятора C2313

"тип1": перехват по ссылке ("тип2") в строке "номер"

Тип исключения имеет два обработчика. Тип второго перехвата — это ссылка на тип первого перехвата.

В следующем примере возникает ошибка C2313:

```
// C2313.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
    try {
        throw "ooops!";
    }
    catch( C& ) {}
    catch( C ) {}   // C2313
}
```