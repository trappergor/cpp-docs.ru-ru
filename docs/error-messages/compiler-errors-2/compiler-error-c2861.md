---
title: Ошибка компилятора C2861 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94210350e0483b46eb86579b837501a5291bda4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037259"
---
# <a name="compiler-error-c2861"></a>Ошибка компилятора C2861

«имя функции»: функция-член интерфейса не может быть определен

Компилятор обнаружил ключевое слово интерфейс или определить структуры как интерфейс, но затем найти член определение функции.  Интерфейс не может содержать определение для функции-члена.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2861:

```
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861

```