---
title: Ошибка компилятора C2833 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53360c1eaf81ad407589fbdb125d9e6fe017708e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070175"
---
# <a name="compiler-error-c2833"></a>Ошибка компилятора C2833

«оператор» не является распознаваемым оператором или типом

Слово `operator` должен следовать оператор, который вы хотите переопределить или типом, который требуется преобразовать.

Список операторов, которые можно определить в управляемом типе, см. в разделе [определяемых пользователем операторов](../../dotnet/user-defined-operators-cpp-cli.md).

Следующий пример приводит к возникновению ошибки C2833:

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```