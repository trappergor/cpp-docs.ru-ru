---
title: Неустранимая ошибка C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: b6253af9fcf400321fb58d4d8a6d7aacf461b926
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174204"
---
# <a name="fatal-error-c1103"></a>Неустранимая ошибка C1103

неустранимая ошибка при импорте progid: "сообщение"

Компилятор обнаружил проблему при импорте библиотеки типов.  Например, нельзя указать библиотеку типов с помощью progid и в то же время указать `no_registry`.

Дополнительные сведения см. в разделе [директива #import](../../preprocessor/hash-import-directive-cpp.md).

Следующий пример приводит к возникновению ошибки C1103:

```
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```