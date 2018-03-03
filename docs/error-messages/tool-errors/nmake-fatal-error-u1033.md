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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94f2626e1ce318d83d306595e386f880c62dec3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1033"></a>Неустранимая ошибка NMAKE U1033
Синтаксическая ошибка: Непредвиденная «строка»  
  
 Строка, не входит в допустимый синтаксис файла makefile.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Если закрывающий набор угловых скобок (**<<**) для встроенного файла не в начале строки, возникает следующая ошибка:  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  Если определение макроса в файле makefile содержится знак равенства (**=**) без предшествующий имя или, если имя определяемой макрос @me в пустую строку, возникает следующая ошибка:  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  Если точка с запятой (**;**) в строке комментария в СРЕДСТВАХ. INI расположена не в начале строки, возникает следующая ошибка:  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Если файл makefile был отформатирован с помощью текстовых редакторов, может возникнуть следующая ошибка:  
  
    ```  
    syntax error : ':' unexpected  
    ```