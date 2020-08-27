---
title: Ошибка компилятора C2706
description: Описывает ошибку компилятора Microsoft C/C++ C2706.
ms.date: 08/25/2020
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: 11e1e878f82ad59bb712155747696c0d6c6a239e
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898732"
---
# <a name="compiler-error-c2706"></a>Ошибка компилятора C2706

> Недопустимый `__except` без парности `__try` (отсутствует "}" в `__try` блоке?)

Компилятору не удалось найти закрывающую фигурную скобку для **`__try`** блока.

Следующий пример приводит к возникновению ошибки C2706:

```cpp
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```
