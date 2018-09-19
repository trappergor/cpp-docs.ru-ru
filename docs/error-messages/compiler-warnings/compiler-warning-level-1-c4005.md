---
title: Предупреждение (уровень 1) C4005 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8be172086e316c991f461b3ac42f58739801cfa7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022972"
---
# <a name="compiler-warning-level-1-c4005"></a>Компилятор предупреждение (уровень 1) C4005

«Идентификатор»: макроопределения

Идентификатор макроса определен дважды. Компилятор использует второе определение макроса.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Определение макроса в командной строке и в коде с `#define` директива.

1. Макросы, импортированные из включаемых файлов.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Удалите одно из определений.

1. Используйте [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) директиву перед вторым определением.

Следующий пример приводит к возникновению ошибки C4005:

```
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