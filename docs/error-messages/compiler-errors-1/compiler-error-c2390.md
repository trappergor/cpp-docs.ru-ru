---
title: Ошибка компилятора C2390 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a32a9ca77ba43e5f2866baed91b99103224dbc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198720"
---
# <a name="compiler-error-c2390"></a>Ошибка компилятора C2390
«Идентификатор»: неправильный класс хранения «спецификатор»  
  
 Класс хранения не является допустимым для глобальной области идентификатора. Класс хранения по умолчанию используется вместо недопустимый класс.  
  
 Возможные решения:  
  
-   Если идентификатор является функцией, объявите его с `extern` хранилища.  
  
-   Если идентификатор является формальным параметром или локальной переменной, объявите его с хранилищем автоматически.  
  
-   Если идентификатор является глобальной переменной, объявите его без класса хранения (автоматическая память).  
  
## <a name="example"></a>Пример  
  
-   Следующий пример приводит к возникновению ошибки C2390:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```