---
title: Ошибка компилятора C2191 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2191
dev_langs:
- C++
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e739c5c9fc77c4c9658afb2f5f6d9568c6f43bb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088362"
---
# <a name="compiler-error-c2191"></a>Ошибка компилятора C2191

второй список параметров длиннее первого

Функция C была объявлена во второй раз с более длинный список параметров. C не поддерживает перегруженные функции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2191:

```
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```