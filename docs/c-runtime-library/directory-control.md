---
title: "Управление каталогами | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "элементы управления [C++], каталог"
  - "процедуры управления каталогами"
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Управление каталогами
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти процедуры получают доступ, изменяют и получают информацию о структуре каталогов.  
  
### Процедуры управления каталогами  
  
|Подпрограмма|Применение|Эквивалент в .NET Framework|  
|------------------|----------------|---------------------------------|  
|[\_chdir, \_wchdir](../Topic/_chdir,%20_wchdir.md)|Изменяет текущую рабочую папку|[\<caps:sentence id\="tgt8" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_chdrive](../c-runtime-library/reference/chdrive.md)|Изменяет текущий диск|[\<caps:sentence id\="tgt11" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getcwd, \_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Получает текущую рабочую папку для диска по умолчанию|[\<caps:sentence id\="tgt14" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdcwd, \_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Получает текущую рабочую папку для указанного диска|[\<caps:sentence id\="tgt16" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdiskfree](../Topic/_getdiskfree.md)|Заполняет структуру `_diskfree_t` сведениями о диске.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_getdrive](../c-runtime-library/reference/getdrive.md)|Получает текущий диск \(по умолчанию\)|[\<caps:sentence id\="tgt23" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdrives](../Topic/_getdrives.md)|Возвращает битовую маску, которая представляет доступные в данный момент диски.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_mkdir, \_wmkdir](../Topic/_mkdir,%20_wmkdir.md)|Создает новый каталог|[System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx), [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)|  
|[\_rmdir, \_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Удаляет каталог|[\<caps:sentence id\="tgt32" sentenceid\="de5c5e84e86fdd3cd99296d3b2518f57" class\="tgtSentence"\>System::IO::Directory::Delete\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)|  
|[\_searchenv, \_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [\_searchenv\_s, \_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md)|Выполняет поиск указанного файла в указанных путях|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [Обработка файлов](../c-runtime-library/file-handling.md)   
 [Системные вызовы](../Topic/System%20Calls.md)