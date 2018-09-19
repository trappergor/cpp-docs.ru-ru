---
title: Ошибка компилятора C2561 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8611af23ab884a853fc751ae82c636753993495b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070708"
---
# <a name="compiler-error-c2561"></a>Ошибка компилятора C2561

«Идентификатор»: функция должна возвращать значение

Функция была объявлена как возвращающая значение, но не содержит определение функции `return` инструкции.

Эта ошибка может быть вызвана неверным прототипом функции:

1. Если функция не возвращает значение, объявите функцию с возвращаемым типом [void](../../cpp/void-cpp.md).

1. Проверьте, что все возможные ветви функции возвращают значение типа, объявленные в прототипе.

1. Функции C++, содержащие встроенного ассемблера, в которых хранятся возвращаемое значение в `AX` регистра может потребоваться оператор return. Скопируйте значение в `AX` во временную переменную и верните ее из функции.

Следующий пример приводит к возникновению ошибки C2561:

```
// C2561.cpp
int Test(int x) {
   if (x) {
      return;   // C2561
      // try the following line instead
      // return 1;
   }
   return 0;
}

int main() {
   Test(1);
}
```