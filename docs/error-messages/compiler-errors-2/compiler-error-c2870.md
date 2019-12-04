---
title: Ошибка компилятора C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: 3b006592723df1222d05e39b3bc9e5729efc8aa6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755035"
---
# <a name="compiler-error-c2870"></a>Ошибка компилятора C2870

"имя": определение пространства имен должно находиться либо в области файла, либо непосредственно в пределах другого определения пространства имен

Вы определили `name` пространства имен неправильно. Пространства имен должны быть определены в области видимости файла (вне всех блоков и классов) или непосредственно в другом пространстве имен.

Следующий пример приводит к возникновению ошибки C2870:

```cpp
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```
