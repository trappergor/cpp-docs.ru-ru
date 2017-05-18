---
title: "Неустранимая ошибка NMAKE U1033 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e8cd0591a1b2fac4ac8837f53ac576eb1eae7ed7
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="nmake-fatal-error-u1033"></a>Неустранимая ошибка NMAKE U1033
Синтаксическая ошибка: Непредвиденная «строка»  
  
 Строка, не входит в допустимый синтаксис файла makefile.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Если закрывающий набор угловых скобок (**<<**) для встроенного файла не в начале строки, то происходит следующая ошибка:  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  Если определение макроса в файле makefile содержится знак равенства (**=**) без перед именем или если имя определяемого макрос @me значение nothing, возникает следующая ошибка:  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  Если точка с запятой (**;**) в строке комментария в файле TOOLS. INI расположена не в начале строки, то происходит следующая ошибка:  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Если файл makefile был отформатирован с помощью текстовых редакторов, может возникнуть следующая ошибка:  
  
    ```  
    syntax error : ':' unexpected  
    ```
