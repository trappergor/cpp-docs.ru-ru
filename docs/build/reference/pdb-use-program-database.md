---
title: "/PDB (Использование базы данных программы) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdb"
  - "VC.Project.VCLinkerTool.ProgramDatabaseFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PDB-файлы, создание"
  - "/PDB - параметр компоновщика"
  - "PDB-файлы, создание"
  - "PDB - параметр компоновщика"
  - "-PDB - параметр компоновщика"
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDB (Использование базы данных программы)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDB:filename  
```  
  
## Заметки  
 Здесь:  
  
 *filename*  
 Указанное пользователем имя базы данных программы \(PDB\), созданной компоновщиком.  Заменяет стандартное имя.  
  
## Заметки  
 По умолчанию при указании параметра [\/DEBUG](../../build/reference/debug-generate-debug-info.md) компоновщик создает базу данных программы \(PDB\), которая содержит отладочную информацию.  Стандартное имя файла для PDB содержит имя программы и расширение .pdb.  
  
 Используйте \/PDB:*имя\_файла* для указания имени PDB\-файла.  Если параметр \/DEBUG не определен, параметр \/PDB игнорируется.  
  
 PDB\-файл может иметь размер до 2 ГБ.  
  
 For more information, see [PDB\-файла как входные данные компоновщика](../../build/reference/dot-pdb-files-as-linker-input.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Отладка**.  
  
4.  Измените свойство **Создавать файл базы данных программы**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)