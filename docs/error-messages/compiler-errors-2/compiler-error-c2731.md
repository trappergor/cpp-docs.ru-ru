---
title: Ошибка компилятора C2731 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2731
dev_langs:
- C++
helpviewer_keywords:
- C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85062af79a7de750ca0e347da00f6209e8293074
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028770"
---
# <a name="compiler-error-c2731"></a>Ошибка компилятора C2731

«Идентификатор»: функция не может быть перегружен

Функции `main`, `WinMain`, `DllMain`, и `LibMain` не могут быть перегружены.

Следующий пример приводит к возникновению ошибки C2731:

```
// C2731.cpp
extern "C" void WinMain(int, char *, char *);
void WinMain(int, short, char *, char*);   // C2731
```