---
title: Предупреждение компилятора (уровень 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 71b23ec719198d15a99b4fcfd50db8b151e03226
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627355"
---
# <a name="compiler-warning-level-1-c4005"></a>Предупреждение компилятора (уровень 1) C4005

"идентификатор": Переопределение макроса

Идентификатор макроса определен дважды. Компилятор использует второе определение макроса.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Определение макроса в командной строке и в коде с помощью директивы `#define`.

1. Макросы, импортированные из включаемых файлов.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Удалите одно из определений.

1. Используйте директиву [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) перед вторым определением.

Следующий пример приводит к возникновению ошибки C4005:

```cpp
// C4005.cpp
// compile with: /W1 /EHsc
#include <iostream>
using namespace std;

#define TEST "test1"
#define TEST "test2"   // C4005 delete or rename to resolve the warning

int main() {
   cout << TEST << endl;
}
```