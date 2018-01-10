---
title: "ССЫЛКА входные файлы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d0cae9498d2c9b49e52cf56991d2425de39d7e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="link-input-files"></a>Входные LINK-файлы
Компоновщик предоставить файлы, содержащие объекты, импорта и стандартные библиотеки, ресурсы, определения модулей и ввод команд. СВЯЗЬ не использует расширения файлов для делать предположения о содержимом файла. Вместо этого программа LINK проверяет каждый входной файл, чтобы определить, какого рода файла.  
  
 Объектные файлы в командной строке, обрабатываются в порядке их следования в командной строке. Библиотеки производится в порядке командной строки, а также с использованием следующих механизмов: неразрешенные символы при связывании в объектный файл из библиотеки производится поиск в эту библиотеку во-первых, а затем в следующих библиотеках из командной строки и [/DEFAULTLIB (укажите библиотеку по умолчанию)](../../build/reference/defaultlib-specify-default-library.md) директив и затем все библиотеки, в начало командной строки.  
  
> [!NOTE]
>  ССЫЛКА больше не принимает точку с запятой (или любой другой знак) как начало комментария в файлах ответа и упорядочение файлов. Точки с запятой распознаются только в качестве начального комментарии в файлах определения модуля (.def).  
  
 ССЫЛКИ используются следующие типы входных файлов:  
  
-   [OBJ-файлы](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [NETMODULE-файлы](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [LIB-файлы](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [EXP-файлах](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [DEF-файлы](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [PDB-файлы](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [RES-файлы](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [файлы .exe](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [TXT-файлы](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [ILK-файлы](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)