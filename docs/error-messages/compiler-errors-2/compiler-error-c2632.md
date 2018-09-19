---
title: Ошибка компилятора C2632 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf03c35c60bebb52c94ed04cca2349f35c06fbc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093654"
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