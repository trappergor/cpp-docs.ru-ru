---
title: Ошибка компилятора C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: f61281da23e46236e7fce496a4d89086e5d6c0ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165050"
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