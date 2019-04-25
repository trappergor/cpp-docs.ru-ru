---
title: Ошибка компилятора C2874
ms.date: 11/04/2016
f1_keywords:
- C2874
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
ms.openlocfilehash: 04cbce14fc1fcb1d5bbb07c7f847c479988224a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165104"
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