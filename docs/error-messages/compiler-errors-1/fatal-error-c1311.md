---
title: Неустранимая ошибка C1311 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d93aa28d0cef3c07fd469349d485c4009fa4771d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091066"
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