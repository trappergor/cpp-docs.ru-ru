---
title: Ошибка компилятора C3222 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30231f74b379cd9d69806fbd4b49ba0cb55ad871
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048322"
---
# <a name="compiler-error-c3222"></a>Ошибка компилятора C3222

"parameter": нельзя объявить аргументы по умолчанию для функций-членов управляемого типа, типа WinRT или универсальных функций

Запрещено объявлять параметр метода с аргументом по умолчанию. Перегруженные формы метода — один из способов решения этой проблемы. То есть вам нужно определить метод с тем же именем без параметров и затем инициализировать переменную в теле метода.

Следующий пример приводит к возникновению ошибки C3222:

```
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
