---
title: Ошибка компилятора C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: edca117da585fee731041d696e05af1baf6d3e5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214989"
---
# <a name="compiler-error-c3666"></a>Ошибка компилятора C3666

«конструктор»: спецификатор переопределения «ключевое слово», не допускается в конструкторе

Спецификатор переопределения был использован с помощью конструктора, и что не допускается. Дополнительные сведения см. в разделе [спецификаторы переопределения](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3666.

```
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```