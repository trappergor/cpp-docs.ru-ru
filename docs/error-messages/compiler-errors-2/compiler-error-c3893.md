---
title: Ошибка компилятора C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 20c17eaa6555b5511ecbc930eacdb2ec92475b23
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749507"
---
# <a name="compiler-error-c3893"></a>Ошибка компилятора C3893

"var": использование l-value элемента данных initonly допускается только в конструкторе экземпляра класса "type_name"

Статические члены данных [initonly](../../dotnet/initonly-cpp-cli.md) могут иметь только свои адреса, созданные в статическом конструкторе.

Элементы данных экземпляра (нестатические) initonly могут иметь только свои адреса в конструкторах экземпляров (не статических).

Следующий пример приводит к возникновению ошибки C3893:

```cpp
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```
