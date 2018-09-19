---
title: Ошибка компилятора C3395 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3395
dev_langs:
- C++
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b604db63466df28d951e8c0027d85f55013f4d5a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103429"
---
# <a name="compiler-error-c3395"></a>Ошибка компилятора C3395

«функция»: __declspec(dllexport) невозможно применять функцию с \__clrcall соглашение о вызовах

`__declspec(dllexport)` и [__clrcall](../../cpp/clrcall.md) несовместимы.  Дополнительные сведения см. в разделе [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

Следующий пример приводит к возникновению ошибки C3395:

```
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```