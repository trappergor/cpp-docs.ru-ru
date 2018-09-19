---
title: Ошибка компилятора C2422 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17421f2d4a7823c0e2fbb34a54a7c562223c798c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047035"
---
# <a name="compiler-error-c2422"></a>Ошибка компилятора C2422

Недопустимое переопределение сегмента в «операнд»

Встроенный код ассемблера неправильно использует оператор переопределения сегмента (двоеточие) для операнда.  Возможные причины:

- Регистр, перед оператором не регистр.

- Регистр, перед оператором не только регистром сегмента в операнде.

- Переопределение segment, оператор отображается в оператор косвенного обращения (скобки).

- Выражения, следующего оператора переопределения сегмента не непосредственного операнда или операндов памяти.

Следующий пример приводит к возникновению ошибки C2422:

```
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```