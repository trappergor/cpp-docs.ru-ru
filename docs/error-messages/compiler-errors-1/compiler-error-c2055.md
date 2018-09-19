---
title: Ошибка компилятора C2055 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6c63d79325417fbd9b1f451fb4a51f13957b4df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019346"
---
# <a name="compiler-error-c2055"></a>Ошибка компилятора C2055

требуется список формальных параметров, а не список типов

Определение функции содержит список параметров типа вместо списка формальных параметров. ANSI C требует формальных параметров, чтобы присвоить имя, если они не являются пустыми или многоточием (`...`).

Следующий пример приводит к возникновению ошибки C2055:

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```