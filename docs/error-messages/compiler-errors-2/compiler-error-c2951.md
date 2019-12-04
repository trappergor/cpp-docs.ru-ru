---
title: Ошибка компилятора C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: fdb837f8e9a9b769d470b70b962ce63d144161e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755984"
---
# <a name="compiler-error-c2951"></a>Ошибка компилятора C2951

объявления типов разрешены только в глобальной области видимости, в пространстве имен или на уровне класса

Нельзя объявить универсальный класс или класса шаблона за пределами области глобальных или пространств имен. При внесении универсальных или шаблонных объявлений в включаемый файл убедитесь, что включаемый файл находится в глобальной области видимости.

Следующий пример приводит к возникновению ошибки C2951:

```cpp
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951 также может возникать при использовании универсальных шаблонов:

```cpp
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```
