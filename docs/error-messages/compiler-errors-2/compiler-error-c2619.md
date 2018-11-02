---
title: Ошибка компилятора C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: f82b315a3e7ae4bb1f6d281e1d80ddc2c7fb0dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662922"
---
# <a name="compiler-error-c2619"></a>Ошибка компилятора C2619

identifier: статический элемент данных не допускается в анонимной структуре или объединении

В `static` объявлен элемент анонимной структуры или объединения.

В следующем примере показано возникновение ошибки C2619, а также описывается, как ее устранить, удалив ключевое слово statiс.

```
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```