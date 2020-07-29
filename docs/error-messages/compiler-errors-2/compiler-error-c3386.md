---
title: Ошибка компилятора C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: 0cb6235f1b6bc868655cc6a6ba301be1308402cd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221085"
---
# <a name="compiler-error-c3386"></a>Ошибка компилятора C3386

"тип": __declspec (dllexport)/ \_ _declspec (dllimport) не может применяться к управляемому или винрттипе

`dllimport` [dllexport](../../cpp/dllexport-dllimport.md) **`__declspec`** Модификаторы и "* *" на языке c недопустимы для управляемого или среда выполнения Windowsого типа.

В следующем примере показано возникновение ошибки C3386 и приводятся сведения по ее устранению.

```cpp
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```
