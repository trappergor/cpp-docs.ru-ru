---
title: ССЫЛКА входные файлы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d61a24916c3b56cf666a85483414f86753f7f59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374831"
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