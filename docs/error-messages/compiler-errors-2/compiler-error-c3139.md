---
title: Ошибка компилятора C3139
ms.date: 11/04/2016
f1_keywords:
- C3139
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
ms.openlocfilehash: f224be74a94e0e769e7c26bc99b4790d69f6b65b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521207"
---
# <a name="compiler-error-c3139"></a>Ошибка компилятора C3139

«struct»: невозможно экспортировать UDT без членов

Предпринята попытка применить [Экспорт](../../windows/export.md) атрибут к пустому типу, определяемые пользователем (UDT). Пример:

```
// C3139.cpp
#include "unknwn.h"
[emitidl];
[module(name=xx)];

[export] struct MyStruct {   // C3139 empty type
};
int main(){}
```