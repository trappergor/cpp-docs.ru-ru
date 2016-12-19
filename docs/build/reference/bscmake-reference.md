---
title: "Справочник ВSCMAKE | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "BSC-файлы, построение"
  - "обзор файлов информации (.bsc), построение"
  - "окна обозревателя"
  - "BSC-файлы, построение"
  - "BSCMAKE - программа"
  - "BSCMAKE - программа, справочник"
  - "Вспомогательная утилита просмотра информации Microsoft"
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Справочник ВSCMAKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  Хотя средство BSCMAKE по\-прежнему устанавливается вместе с Visual Studio, оно больше не используется в интегрированной среде разработки.  Начиная с Visual Studio 2008 информация об исходном коде и символах автоматически сохраняется в SDF\-файле SQL Server в папке решения.  
  
 Служебная программа Microsoft Browse Information Maintenance \(BSCMAKE.EXE\) создает файл информации об исходном коде \(BSC\) из SBR\-файлов, созданных во время компиляции.  Вы можете просмотреть файл об исходном коде в обозревателе объектов.  Сведения об обозревателе объектов см. в разделе [Переходы в обозревателе объектов](http://msdn.microsoft.com/ru-ru/53eb91aa-08c6-4299-8e3c-a877ae8d0c55).  
  
 При построении программы можно автоматически создать файл информации об исходном коде, используя программу BSCMAKE.  Вам не требуется знать, как запускать BSCMAKE, если вы создаете файл информации об исходном коде в среде разработки Visual C\+\+.  Тем не менее можно прочитать этот раздел для понимания доступных возможностей.  
  
 При построении программы вне среды разработки вы по\-прежнему можете создать пользовательский BSC\-файл, который можно просмотреть в среде.  Запустите BSCMAKE для SBR\-файлов, созданных во время компиляции.  
  
> [!NOTE]
>  Это средство можно запустить только из командной строки [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  В системной командной строке или проводнике это невозможно.  
  
 Этот раздел содержит следующие подразделы:  
  
-   [Информационные файлы просмотра сборки: общие сведения](../../build/reference/building-browse-information-files-overview.md)  
  
-   [Построение BSC\-файла](../../build/reference/building-a-dot-bsc-file.md)  
  
-   [Командная строка BSCMAKE](../../build/reference/bscmake-command-line.md)  
  
-   [Командный файл BSCMAKE](../../build/reference/bscmake-command-file-response-file.md)  
  
-   [Параметры BSCMAKE](../Topic/BSCMAKE%20Options.md)  
  
-   [Коды выхода BSCMAKE](../Topic/BSCMAKE%20Exit%20Codes.md)  
  
## См. также  
 [Средства построения С\/C\+\+](../Topic/C-C++%20Build%20Tools.md)