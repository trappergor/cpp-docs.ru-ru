---
title: Ошибка компилятора C2869 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2869
dev_langs:
- C++
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a899826ab299665a7a44deaa89416affe5d41f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101518"
---
# <a name="compiler-error-c2869"></a>Ошибка компилятора C2869

«name»: уже был определен как пространство имен

Невозможно использовать имя уже используется как пространство имен.

Следующий пример приводит к возникновению ошибки C2869:

```
// C2869.cpp
// compile with: /c
namespace A { int i; };

class A {};   // C2869, A is already used
```