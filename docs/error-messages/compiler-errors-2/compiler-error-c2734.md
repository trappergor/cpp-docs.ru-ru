---
title: Ошибка компилятора C2734 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2734
dev_langs:
- C++
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc3322d97761f1a463426c71bde58de3591ded4a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100712"
---
# <a name="compiler-error-c2734"></a>Ошибка компилятора C2734

«Идентификатор»: объект const необходимо инициализировать, если не extern

Идентификатор объявлен `const` , но не инициализирован или `extern`.

Следующий пример приводит к возникновению ошибки C2734:

```
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```