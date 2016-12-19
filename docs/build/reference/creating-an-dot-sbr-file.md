---
title: "Создание SBR-файла | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SBR-файлы"
  - "BSCMAKE - программа, входные файлы"
  - "локальные символы в файлах просмотра информации"
  - "SBR-файлы"
  - "файлы обозревателя исходного кода"
  - "символы"
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Создание SBR-файла
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Входными файлами для BSCMAKE являются SBR\-файлы.  Компилятор создает SBR\-файл для каждого объектного файла \(OBJ\), который он компилирует.  При создании или обновлении вашего файла доступа к информации все SBR\-файлы для вашего проекта должны быть доступны на диске.  
  
 Чтобы создать SBR\-файл со всей возможной информацией, укажите [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).  
  
 Чтобы создать SBR\-файл, не содержащий локальных символов, укажите [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md).  Если SBR\-файлы содержат локальные символы, можно удалить их из файла BSC при помощи BSCMAKE параметра [\/El option](../Topic/BSCMAKE%20Options.md)`.`  
  
 Можно создать SBR\-файл, не выполняя полную компиляцию.  Например, можно указать параметр \/Zs, чтобы компилятор выполнил синтаксическую проверку и создал SBR\-файл, если указано \/FR или \/Fr.  
  
 Процесс построения можно сделать более эффективным, если SBR\-файлы сначала упаковать, чтобы удалить определения, ссылка на которые отсутствует.  Компилятор автоматически упаковывает SBR\-файлы.  
  
## См. также  
 [Построение BSC\-файла](../../build/reference/building-a-dot-bsc-file.md)