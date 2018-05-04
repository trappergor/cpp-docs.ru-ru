---
title: Создание. SBR-файл | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdada1f4d07d02988da388e39e332c832f633adb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="creating-an-sbr-file"></a>Создание SBR-файла
Входные файлы для BSCMAKE можно SBR-файлов. Компилятор создает SBR-файл для каждого объекта файла (.obj), он компилируется. При построении или обновить файл доступа к информации все SBR-файлы для проекта должен быть доступен на диске.  
  
 Чтобы создать SBR-файл со всеми данными, возможно, укажите [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).  
  
 Чтобы создать SBR-файл, который не содержит локальные символы, укажите [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md). Если SBR-файлы содержат локальные символы, можно удалить их из BSC-файл с помощью BSCMAKE [параметр /El](../../build/reference/bscmake-options.md)`.`  
  
 Можно создать SBR-файл, не выполняя полную компиляцию. Например можно указать /Zs-параметр компилятора для выполнения проверки синтаксиса и по-прежнему создать SBR-файл, если указано /FR или/fr.  
  
 Процесс построения может быть более эффективным, если SBR-файлы сначала упаковать, чтобы удалить неиспользуемые определения. Компилятор автоматически упаковывает SBR-файлов.  
  
## <a name="see-also"></a>См. также  
 [Сборка BSC-файла](../../build/reference/building-a-dot-bsc-file.md)