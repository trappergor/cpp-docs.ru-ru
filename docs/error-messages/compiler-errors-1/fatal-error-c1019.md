---
title: Неустранимая ошибка C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: 2d8e63510b762b0de0cda50ab7a03b773dfb949a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383130"
---
# <a name="fatal-error-c1019"></a>Неустранимая ошибка C1019

непредвиденный #else

Директива `#else` находится за пределами конструкции `#if`, `#ifdef`или `#ifndef` . Используйте `#else` только в одной из этих конструкций.

При компиляции следующего примера возникнет ошибка C1019:

```
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

Возможное решение

```
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```