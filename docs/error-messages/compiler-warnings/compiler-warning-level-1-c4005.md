---
title: Предупреждение (уровень 1) C4005 компилятора | Документы Microsoft
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
ms.openlocfilehash: 3a06ea88dab6ac7e89f7d53351b54593fd7bd232
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275380"
---
# <a name="compiler-warning-level-1-c4005"></a>Предупреждение (уровень 1) C4005 компилятора
«Идентификатор»: переопределение макросов  
  
 Идентификатор макроса определен дважды. Компилятор использует второе определение макроса.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Определение макроса в командной строке и в коде с `#define` директивы.  
  
2.  Импорт макроса из включаемых файлов.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Удалите одно из определений.  
  
2.  Используйте [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) директиву перед вторым определением.  
  
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