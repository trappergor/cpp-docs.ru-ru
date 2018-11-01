---
title: Ошибка компилятора C2874
ms.date: 11/04/2016
f1_keywords:
- C2874
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
ms.openlocfilehash: 04cbce14fc1fcb1d5bbb07c7f847c479988224a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514781"
---
# <a name="compiler-error-c2874"></a>Ошибка компилятора C2874

с помощью объявление вызвало наличие нескольких объявлений для «символ»

Объявление вызывает один и тот же элемент определяется два раза.

Следующий пример приводит к возникновению ошибки C2874:

```
// C2874.cpp
namespace Z {
   int i;
}

int main() {
   int i;
   using Z::i;   // C2874, i already declared
}
```