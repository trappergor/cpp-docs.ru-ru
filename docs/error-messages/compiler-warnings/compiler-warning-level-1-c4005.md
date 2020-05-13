---
title: Предупреждение компилятора (уровень 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 4e95f8deeb61c5a4d56e0643beb6a746f848e33e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164733"
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
