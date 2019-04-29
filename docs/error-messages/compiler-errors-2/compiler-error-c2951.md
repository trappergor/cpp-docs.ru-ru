---
title: Ошибка компилятора C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: dbc7186edfce6cc12a38fb2fc1dda08ac4a181c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300730"
---
# <a name="compiler-error-c2951"></a>Ошибка компилятора C2951

объявления типов допускаются только в глобальной, пространство имен и области класса

Можно объявить универсальный класс или класс шаблона за пределами глобального или области видимости пространства имен. Если во включаемом файле объявлениях универсального класса или шаблона, убедитесь, что включаемого файла находится в глобальной области.

Следующий пример приводит к возникновению ошибки C2951:

```
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951 также может возникнуть при использовании универсальных шаблонов:

```
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```