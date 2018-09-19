---
title: Ошибка компилятора C2491 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40e6adfc369cd79f4c08c9099f5bc7db2b2281d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110995"
---
# <a name="compiler-error-c2491"></a>Ошибка компилятора C2491

'идентификатор' : определение функции dllimport не разрешено

Данные, статические данные-члены могут быть объявлены, как `dllimport`, но не определены как `dllimport`.

Чтобы устранить эту проблему, удалите описатель `__declspec(dllimport)` из определения функции.

Следующий пример приводит к возникновению ошибки C2491:

```
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```