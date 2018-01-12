---
title: "Определения модуля (. Файлы DEF) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49f5eb5b75bad22b59cb4fbb98554bbfd44d13b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="module-definition-def-files"></a>Файлы определения модуля (DEF)
Файлы определения модуля (DEF) предоставляют компоновщику сведения о экспорты, атрибуты и другие сведения о программе должна быть установлена связь. DEF-файл может пригодиться при построении библиотеки DLL. Так как существуют [параметры компоновщика](../../build/reference/linker-options.md) может использоваться вместо операторов определения модуля, DEF-файлы обычно не требуются. Можно также использовать [__declspec(dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) как способ указания экспортированных функций.  
  
 DEF-файл можно вызывать во время фазы компоновщика с [/DEF (указание файла определения модуля)](../../build/reference/def-specify-module-definition-file.md) компоновщика.  
  
 При создании файла .exe, не имеющего экспортов, с помощью DEF-файла сделает Загрузка файла в выходных данных большего размера и медленнее.  
  
 Пример см. в разделе [Экспорт из библиотеки DLL с использованием DEF-файлы](../../build/exporting-from-a-dll-using-def-files.md).  
  
 См. в следующих разделах содержатся дополнительные сведения:  
  
-   [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [EXPORTS](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [LIBRARY](../../build/reference/library.md)  
  
-   [ИМЯ](../../build/reference/name-c-cpp.md)  
  
-   [РАЗДЕЛЫ](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [STUB](../../build/reference/stub.md)  
  
-   [ВЕРСИЯ](../../build/reference/version-c-cpp.md)  
  
-   [Зарезервированные слова](../../build/reference/reserved-words.md)  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о построении C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)  