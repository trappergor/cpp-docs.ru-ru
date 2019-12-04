---
title: Неустранимая ошибка C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: f037d1acb281b5997e3486a542784abc4b4b7542
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747388"
---
# <a name="fatal-error-c1103"></a>Неустранимая ошибка C1103

неустранимая ошибка при импорте progid: "сообщение"

Компилятор обнаружил проблему при импорте библиотеки типов.  Например, нельзя указать библиотеку типов с помощью progid и в то же время указать `no_registry`.

Дополнительные сведения см. в разделе [директива #import](../../preprocessor/hash-import-directive-cpp.md).

Следующий пример приводит к возникновению ошибки C1103:

```cpp
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```
