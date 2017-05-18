---
title: "Имена среды | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e27637b911ebab5552974dd8fc6e7c9637c192a0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="environment-names"></a>Имена сред
**ANSI 4.10.4.4** Набор имен среды и метод, который используется для изменения списка среды, используемого функцией [getenv](../c-runtime-library/reference/getenv-wgetenv.md)  
  
 Набор имен среды не ограничен.  
  
 Чтобы изменить переменные среды из программы на языке C, вызовите функцию [_putenv](../c-runtime-library/reference/putenv-wputenv.md). Чтобы изменить переменные среды из командной строки в Windows, используйте команду SET (например, SET LIB = D:\ LIBS).  
  
 Переменные среды, заданные в программе на языке C, существуют, только пока выполняется копия узла командной оболочки операционной системы (CMD.EXE или COMMAND.COM). Например, в строке  
  
```  
system( SET LIB = D:\LIBS );  
```  
  
 выполняется копия командной оболочки (CMD.EXE), задается переменная среды LIB и выполняется возврат в программу на языке C при выходе из дополнительной копии CMD.EXE. При выходе из этой копии CMD.EXE временная переменная среды LIB удаляется.  
  
 Таким же образом, изменения, выполненные функцией `_putenv`, действуют только до завершения программы.  
  
## <a name="see-also"></a>См. также  
 [Library Functions](../c-language/library-functions.md)  (Функции библиотеки)  
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)
