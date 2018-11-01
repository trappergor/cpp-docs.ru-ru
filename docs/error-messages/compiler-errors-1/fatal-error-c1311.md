---
title: Неустранимая ошибка C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: ba2b797c9bf521533e7c2ccff8d358b6216d392f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637909"
---
# <a name="fatal-error-c1311"></a>Неустранимая ошибка C1311

Формат COFF не может статическую инициализацию «var» с байтах адреса

Адрес, значение которого неизвестен во время компиляции не может назначаться статически переменной, тип которого имеет хранилище размером менее четырех байт.

Эта ошибка может возникать в коде, который в противном случае допустимый C++.

В следующем примере показано одно условие, которое может привести к C1311.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```