---
title: Ошибка компилятора C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: f61281da23e46236e7fce496a4d89086e5d6c0ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546382"
---
# <a name="compiler-error-c2870"></a>Ошибка компилятора C2870

«name»: определение пространства имен должно отображаться либо в области видимости файла, или непосредственно в другом определении пространства имен

Пространства имен `name` неправильно. Пространства имен должны быть определены в области видимости файла (вне всех блоков и классов) или непосредственно в другое пространство имен.

Следующий пример приводит к возникновению ошибки C2870:

```
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```