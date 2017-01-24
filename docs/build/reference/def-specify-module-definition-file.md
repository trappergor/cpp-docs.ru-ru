---
title: "/DEF (указание файла определения модуля) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ModuleDefinitionFile"
  - "/def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEF - параметр компоновщика"
  - "DEF - параметр компоновщика"
  - "-DEF - параметр компоновщика"
  - "файлы определения модулей"
  - "файлы определения модулей, определение"
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEF (указание файла определения модуля)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEF:filename  
```  
  
## Заметки  
 Здесь:  
  
 *filename*  
 Имя файла определения модуля \(DEF\) для передачи в компоновщик.  
  
## Заметки  
 Параметр \/DEF передает файл определения модуля \(.def\) в компоновщик.  Только DEF\-файл можно указать для параметра LINK.  Дополнительные сведения о DEF\-файлах см. в разделе [Файлы определения модулей](../Topic/Module-Definition%20\(.Def\)%20Files.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Ввод**.  
  
4.  Измените значение свойства **Файл определения модуля**.  
  
 Чтобы указать DEF\-файл из среды разработки, следует добавить его в проект наряду с остальными файлами, а затем указать данный файл в параметре \/DEF.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)