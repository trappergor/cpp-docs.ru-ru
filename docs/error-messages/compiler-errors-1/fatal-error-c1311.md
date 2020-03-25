---
title: Неустранимая ошибка C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: e57e4e0899a5f9d81e87a203b1b699cef0884f0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203272"
---
# <a name="fatal-error-c1311"></a>Неустранимая ошибка C1311

Формат COFF не может статически инициализировать "var" с числом байт в адресе

Адрес, значение которого неизвестно во время компиляции, не может быть статически назначен переменной, тип которой имеет размер хранения менее четырех байт.

Эта ошибка может возникать в коде, который в C++противном случае является допустимым.

В следующем примере показано одно условие, которое может вызвать C1311.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
