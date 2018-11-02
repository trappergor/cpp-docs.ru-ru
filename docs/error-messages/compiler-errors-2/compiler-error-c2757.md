---
title: Ошибка компилятора C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: 98b43a2f3c0888fc385226cd80889b9911c84690
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668524"
---
# <a name="compiler-error-c2757"></a>Ошибка компилятора C2757

«символ»: символ с таким именем уже существует и поэтому это имя не может использоваться как имя пространства имен

Символ, используемый в текущей компиляции, так как идентификатор пространства имен уже используется в связанной сборке.

Следующий пример приводит к возникновению ошибки C2757:

```
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

Затем:

```
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
