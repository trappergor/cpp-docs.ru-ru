---
title: Предупреждение компилятора (уровень 1) C4835 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4835
dev_langs:
- C++
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70492be13d312c5d167990cfa0b6c0d741e1055f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080107"
---
# <a name="compiler-warning-level-1-c4835"></a>Предупреждение компилятора (уровень 1) C4835

«переменная»: инициализатор экспортированных данных не будет выполнено до управляемого кода сначала в базовой сборке

При доступе к данным управляемых компонентов, рекомендуется не использовать собственного C++ импорта и экспорта механизмы. Вместо этого объявите элементы данных в управляемый тип и ссылаться на метаданные с `#using` в клиенте. Дополнительные сведения см. в разделе [Директива using](../../preprocessor/hash-using-directive-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4835.

```
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

## <a name="example"></a>Пример

В следующем примере используется компонента, созданного в предыдущем примере, показывающий, что значения переменных отличается от ожидаемого.

```
// C4835_b.cpp
// compile with: /clr C4835.lib
#include <stdio.h>
__declspec(dllimport) int m;
__declspec(dllimport) int *p;

int main() {
   printf("%d\n", m);
   printf("%d\n", p);
}
```

```Output
0
268456008
```