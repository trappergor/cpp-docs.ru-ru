---
title: Ошибка компилятора C2041 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2041
dev_langs:
- C++
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bee199ea3ddca7ae329fc17ed6c3c013dc460eb7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082174"
---
# <a name="compiler-error-c2041"></a>Ошибка компилятора C2041

Недопустимая цифра «character» для основания «число»

Указанный символ не является допустимой цифрой для основания (например, восьмеричной или hex).

Следующий пример приводит к возникновению ошибки C2041:

```
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

Возможное решение

```
// C2041b.cpp
// compile with: /c
int j = 071;
```