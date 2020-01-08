---
title: Ошибка компилятора C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: 66b7d70b9010855ada7b9d24fba80915450a685b
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301877"
---
# <a name="compiler-error-c2191"></a>Ошибка компилятора C2191

второй список параметров длиннее первого

Функция C была объявлена второй раз с более длинным списком параметров. C не поддерживает перегруженные функции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2191:

```c
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```
