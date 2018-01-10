---
title: "Имена среды | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efae64f64ef6b5ed92dffafb9f83a0e32ab38513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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