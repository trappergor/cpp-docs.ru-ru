---
title: Ошибка компилятора C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 9cb6e4d5891c5aefc9d66e7d70a5cd7685ccd393
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302046"
---
# <a name="compiler-error-c2055"></a>Ошибка компилятора C2055

Ожидался список формальных параметров, а не список типов

Определение функции содержит список типов параметров, а не список формальных параметров. ANSI C требует, чтобы формальные параметры были именованы, если они не являются void или многоточием (`...`).

Следующий пример приводит к возникновению ошибки C2055:

```c
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```
