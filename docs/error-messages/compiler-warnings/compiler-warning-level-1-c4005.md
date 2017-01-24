---
title: "Предупреждение компилятора (уровень 1) C4005 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4005"
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": изменение макроопределения  
  
 Идентификатор макроса определен дважды.  При компиляции используется второе определение макроса.  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Определение макроса в командной строке и коде с помощью директивы `#define`.  
  
2.  Импорт макроса из включаемых файлов.  
  
### Возможные способы устранения данной ошибки  
  
1.  Удаление одного из определений.  
  
2.  Использование директивы [\#undef](../../preprocessor/hash-undef-directive-c-cpp.md) перед вторым определением.  
  
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