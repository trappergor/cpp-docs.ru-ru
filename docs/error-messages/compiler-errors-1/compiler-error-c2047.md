---
title: Ошибка компилятора C2047
ms.date: 11/04/2016
f1_keywords:
- C2047
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
ms.openlocfilehash: 50a8ce4ab9d88312b7f91ebb9df068a07fa21aa6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408879"
---
# <a name="compiler-error-c2047"></a>Ошибка компилятора C2047

недопустимый вариант, используемый по умолчанию

Ключевое слово `default` может использоваться только в операторе `switch` .

При компиляции следующего примера возникнет ошибка C2047:

```
// C2047.cpp
int main() {
   int i = 0;
   default:   // C2047
   switch(i) {
      case 0:
      break;
   }
}
```

Возможное решение

```
// C2047b.cpp
int main() {
   int i = 0;
   switch(i) {
      case 0:
      break;
      default:
      break;
   }
}
```