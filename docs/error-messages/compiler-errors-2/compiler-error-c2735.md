---
title: Ошибка компилятора C2735
ms.date: 11/04/2016
f1_keywords:
- C2735
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
ms.openlocfilehash: 73d5f61b5f86153db74a970d97b4656fb662bdad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447861"
---
# <a name="compiler-error-c2735"></a>Ошибка компилятора C2735

Ключевое слово «ключевое_слово» является недопустимым в спецификаторе типа формального параметра

Ключевое слово является недопустимым в данном контексте.

Следующий пример приводит к возникновению ошибки C2735:

```
// C2735.cpp
void f(inline int){}   // C2735
```