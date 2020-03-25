---
title: Предупреждение компилятора (уровень 1) C4835
ms.date: 11/04/2016
f1_keywords:
- C4835
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
ms.openlocfilehash: f86fcaea8a742c19ce175a453c06669178ed2145
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174860"
---
# <a name="compiler-warning-level-1-c4835"></a>Предупреждение компилятора (уровень 1) C4835

"переменная": инициализатор экспортируемых данных не будет выполняться до первого выполнения управляемого кода в сборке узла

При доступе к данным между управляемыми компонентами рекомендуется не использовать собственные C++ механизмы импорта и экспорта. Вместо этого объявите элементы данных внутри управляемого типа и соберите ссылки на метаданные с `#using` в клиенте. Дополнительные сведения см. в разделе [Директива using](../../preprocessor/hash-using-directive-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4835.

```cpp
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

## <a name="example"></a>Пример

В следующем примере используется компонент, встроенный в предыдущем примере, показывающий, что значения переменных не так, как ожидалось.

```cpp
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
