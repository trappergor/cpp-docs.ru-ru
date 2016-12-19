---
title: "/OUT (имя выходного файла) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OutputFile"
  - "/out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OUT C++ - параметр компоновщика"
  - "компоновщик [C++], выходные файлы"
  - "OUT - параметр компоновщика"
  - "-OUT - параметр компоновщика"
  - "выходные файлы, имя - параметр компоновщика"
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /OUT (имя выходного файла)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/OUT:filename  
```  
  
## Заметки  
 Здесь:  
  
 *filename*  
 Указанное пользователем имя выходного файла.  Заменяет стандартное имя.  
  
## Заметки  
 Параметр \/OUT переопределяет стандартное имя и место программы, создаваемые компоновщиком.  
  
 По умолчанию компоновщик формирует имя файла по базовому имени первого указанного файла OBJ и соответствующего расширения \(EXE или DLL\).  
  
 Этот параметр определяет базовое имя по умолчанию для файла сопоставления MAPFILE или для библиотеки импорта.  Дополнительные сведения см. в разделе [Создание файла сопоставлений](../../build/reference/map-generate-mapfile.md) \(\/MAP\) и в разделе [\/IMPLIB](../Topic/-IMPLIB%20\(Name%20Import%20Library\).md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Щелкните страницу свойств **Общие**.  
  
4.  Измените значение свойства **Выходной файл**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)