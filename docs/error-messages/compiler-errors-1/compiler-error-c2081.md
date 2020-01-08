---
title: Ошибка компилятора C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: 2e8e813d8162b9a191b6760366b52783e7c8609f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301994"
---
# <a name="compiler-error-c2081"></a>Ошибка компилятора C2081

"идентификатор": недопустимое имя в списке формальных параметров

Идентификатор привел к синтаксической ошибке.

Эта ошибка может быть вызвана использованием старого стиля для списка формальных параметров. В списке формальных параметров необходимо указать тип формальных параметров.

Следующий пример приводит к возникновению ошибки C2081:

```c
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

Возможное решение:

```c
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```
