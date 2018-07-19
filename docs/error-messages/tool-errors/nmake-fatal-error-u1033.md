---
title: Неустранимая ошибка NMAKE U1033 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d39d4c35ec66d405d51d601b7c5d2b2ab37b02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319274"
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