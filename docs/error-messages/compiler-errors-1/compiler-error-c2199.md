---
title: Ошибка компилятора C2199 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2199
dev_langs:
- C++
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 616b155ad0ca22c3eb45fd881a22ff36b5430f81
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083661"
---
# <a name="compiler-error-c2199"></a>Ошибка компилятора C2199

Синтаксическая ошибка: найдено "идентификатор (" в глобальной области видимости (было объявление действительно требовалось?)

Указанный контекст является причиной синтаксической ошибки. Возможно, некорректный синтаксис объявления.

Следующий пример приводит к возникновению ошибки C2199:

```
// C2199.cpp
// compile with: /c
int j = int(1) int(1);   // C2199
int j = 1;   // OK
```