---
title: Ошибка компилятора C3189
ms.date: 11/04/2016
f1_keywords:
- C3189
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
ms.openlocfilehash: b2de290178657ae427b5ad7999c511ae7ff9f1eb
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781891"
---
# <a name="compiler-error-c3189"></a>Ошибка компилятора C3189

"typeid\<введите абстрактный декларатор >": этот синтаксис больше не поддерживается, используйте:: typeid вместо

Устаревшая форма [typeid](../../extensions/typeid-cpp-component-extensions.md) было использовать, используйте новую форму.

Следующий пример приводит к возникновению ошибки C3189:

```
// C3189.cpp
// compile with: /clr
int main() {
   System::Type^ t  = typeid<System::Object>;   // C3189
   System::Type^ t2  = System::Object::typeid;   // OK
}
```