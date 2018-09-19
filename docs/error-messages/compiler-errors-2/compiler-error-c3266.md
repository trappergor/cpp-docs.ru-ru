---
title: Ошибка компилятора C3266 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3266
dev_langs:
- C++
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1c796f4784c61fc38a725112b40781f30fa6926
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069564"
---
# <a name="compiler-error-c3266"></a>Ошибка компилятора C3266

"класс": список параметров конструктора класса должен иметь тип "void"

Конструкторы классов, программируемых с использованием параметра /clr, не могут принимать параметры.

Следующий пример приводит к возникновению ошибки C3266:

```
// C3266.cpp
// compile with: /clr

ref class X {
   static X(int i) { // C3266
   // try the following line instead
   // static X() {
   }
};

int main() {
}
```
