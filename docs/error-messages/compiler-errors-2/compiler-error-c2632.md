---
title: Ошибка компилятора C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b92d44bcfd04d4de7b39c5bdab5ee146d9b6693b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257638"
---
# <a name="compiler-error-c2632"></a>Ошибка компилятора C2632

«тип1» следуют «тип2» не допускается

Это ошибка может возникать, если отсутствует код между двумя спецификаторами.

Следующий пример приводит к возникновению ошибки C2632:

```
// C2632.cpp
int float i;   // C2632
```

Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003. `bool` Теперь является правильным типом. В предыдущих версиях `bool` представлял собой typedef, и можно было создать идентификаторы с таким именем.

Следующий пример приводит к возникновению ошибки C2632:

```
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Чтобы устранить эту ошибку, так что код является допустимым в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET, переименуйте идентификатор.