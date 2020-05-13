---
title: Предупреждение компилятора (уровень 3) C4310
ms.date: 11/04/2016
f1_keywords:
- C4310
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
ms.openlocfilehash: 1a6088d3d95eada30507ceddbb97701bd3347d93
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198839"
---
# <a name="compiler-warning-level-3-c4310"></a>Предупреждение компилятора (уровень 3) C4310

приведение усекает постоянное значение

Константное значение приводится к меньшему типу. Компилятор выполняет приведение, которое усекает данные. Следующий пример приводит к возникновению ошибки C4310:

```cpp
// C4310.cpp
// compile with: /W4
int main() {
   long int a;
   a = (char) 128;   // C4310, use value 0-127 to resolve
}
```
