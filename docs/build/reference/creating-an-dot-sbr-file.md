---
title: "Создание. SBR-файл | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d87b71daaf5d7b37e67c2c0e56e844bd5251a490
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-sbr-file"></a>Создание SBR-файла
Входные файлы для BSCMAKE можно SBR-файлов. Компилятор создает SBR-файл для каждого объекта файла (.obj), он компилируется. При построении или обновить файл доступа к информации все SBR-файлы для проекта должен быть доступен на диске.  
  
 Чтобы создать SBR-файл со всеми данными, возможно, укажите [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).  
  
 Чтобы создать SBR-файл, который не содержит локальные символы, укажите [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md). Если SBR-файлы содержат локальные символы, можно удалить их из BSC-файл с помощью BSCMAKE [параметр /El](../../build/reference/bscmake-options.md)`.`  
  
 Можно создать SBR-файл, не выполняя полную компиляцию. Например можно указать /Zs-параметр компилятора для выполнения проверки синтаксиса и по-прежнему создать SBR-файл, если указано /FR или/fr.  
  
 Процесс построения может быть более эффективным, если SBR-файлы сначала упаковать, чтобы удалить неиспользуемые определения. Компилятор автоматически упаковывает SBR-файлов.  
  
## <a name="see-also"></a>См. также  
 [Сборка BSC-файла](../../build/reference/building-a-dot-bsc-file.md)