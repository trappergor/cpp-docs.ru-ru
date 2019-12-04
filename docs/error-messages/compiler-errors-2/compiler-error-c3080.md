---
title: Ошибка компилятора C3080
ms.date: 11/04/2016
f1_keywords:
- C3080
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
ms.openlocfilehash: 74a5f33a3b6b6524b53b15067c722c19c0e3f04e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756712"
---
# <a name="compiler-error-c3080"></a>Ошибка компилятора C3080

"функция_метода_завершения": метод завершения не может иметь спецификатор класса хранения

Дополнительные сведения см. [в разделе Деструкторы и методы завершения в статье инструкции: определение и использование классов и структур (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3080.

```cpp
// C3080.cpp
// compile with: /clr /c
ref struct rs {
protected:
   static !rs(){}   // C3080
   !rs(){}   // OK
};
```
