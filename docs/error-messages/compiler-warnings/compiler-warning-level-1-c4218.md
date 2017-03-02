---
title: "Предупреждение (уровень 1) C4218 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6f657da21a7756973b9f9febe823003ebfd68fd1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4218"></a>Предупреждение компилятора (уровень 4) C4218
нестандартное расширение: необходимо указать по крайней мере класс хранения или тип  
  
 При использовании расширений Microsoft по умолчанию (/Ze) можно объявить переменную, не указывая тип или класс хранения. Значение по умолчанию — `int`.  
  
## <a name="example"></a>Пример  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 Такие объявления недопустимы в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
