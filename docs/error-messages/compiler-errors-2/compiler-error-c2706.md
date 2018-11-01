---
title: Ошибка компилятора C2706
ms.date: 11/04/2016
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: 9767d36d44b99423d600d299d0803901d3dbfec5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472518"
---
# <a name="compiler-error-c2706"></a>Ошибка компилятора C2706

Недопустимый __except без соответствующего \__try (отсутствует "}" в \_блок _try?)

Компилятору не удалось найти закрывающую фигурную скобку для `__try` блока.

Следующий пример приводит к возникновению ошибки C2706:

```
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```