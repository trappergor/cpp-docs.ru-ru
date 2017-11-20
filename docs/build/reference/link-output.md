---
title: "Выходные данные LINK | Документы Microsoft"
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
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d01f19f31f83324beab1e44efe181086d6432175
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="link-output"></a>Выходные данные LINK
Выходные данные Link включает файлы .exe, библиотеки DLL, файлы сопоставления и сообщения.  
  
##  <a name="_core_output_files"></a>Выходные файлы  
 Выходной файл по умолчанию, перейдя по ССЫЛКЕ представляет собой файл .exe. Если [/DLL](../../build/reference/dll-build-a-dll.md) параметр указан, программа LINK создает DLL-файл. Можно задать имя выходного файла с [имя выходного файла (/ OUT)](../../build/reference/out-output-file-name.md) параметр.  
  
 В инкрементном режиме LINK создает ILK-файл, сведения о состоянии для дальнейших последовательных построений программы. Дополнительные сведения о ILK-файлах см. в разделе [ILK-файлы](../../build/reference/dot-ilk-files-as-linker-input.md). Дополнительные сведения об инкрементной компоновке см. в разделе [постепенно связи (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) параметр.  
  
 LINK создает программу, содержащую экспортирует (обычно DLL), также производится построение LIB-файл, если файл EXP использовался в сборке. Можно задать имя файла библиотеки импорта с [/IMPLIB](../../build/reference/implib-name-import-library.md) параметр.  
  
 Если [Создание файла сопоставления (/ MAP)](../../build/reference/map-generate-mapfile.md) параметр указан, LINK создает файл сопоставления.  
  
 Если [создать отладочную информацию (/ DEBUG)](../../build/reference/debug-generate-debug-info.md) параметр указан, LINK создает PDB-ФАЙЛ содержит отладочную информацию для программы.  
  
##  <a name="_core_other_output"></a>Прочие выходные данные  
 При вводе `link` без любые другие данные в командной строке, ссылка отображает сводную информацию об используемых параметрах.  
  
 ССЫЛКА отображает сообщение версии и авторских правах и выводит командного файла ввода, если не [отключить загрузочное объявление (/ NOLOGO)](../../build/reference/nologo-suppress-startup-banner-linker.md) используется параметр.  
  
 Можно использовать [печать сообщений о ходе выполнения (/ VERBOSE)](../../build/reference/verbose-print-progress-messages.md) параметр для отображения дополнительных сведений о сборке.  
  
 LINK выдает сообщения об ошибках и предупреждения в виде LNK*nnnn*. Этот префикс ошибки и диапазон номеров также используются LIB, DUMPBIN и EDITBIN.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)