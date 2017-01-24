---
title: "/PDBSTRIPPED (удалить закрытые символы) | Microsoft Docs"
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
  - "/pdbstripped"
  - "VC.Project.VCLinkerTool.StripPrivateSymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PDB-файлы, пропустить закрытые символы"
  - "/PDBSTRIPPED - параметр компоновщика"
  - "PDB-файлы, пропустить закрытые символы"
  - "PDBSTRIPPED - параметр компоновщика"
  - "-PDBSTRIPPED - параметр компоновщика"
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDBSTRIPPED (удалить закрытые символы)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## Заметки  
 Здесь:  
  
 *pdb\_file\_name*  
 Указанное пользователем имя базы данных программы \(PDB\), создаваемой компоновщиком путем удаления закрытых символов.  
  
## Заметки  
 Параметр \/PDBSTRIPPED создает второй файл базы данных программы \(PDB\) при построении образа программы с любыми параметрами компилятора или компоновщика, создающими PDB\-файл \([\/DEBUG](../../build/reference/debug-generate-debug-info.md), [\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md), \/Zd или \/Zi\).  Второй PDB\-файл не содержит символов, которые нежелательно передавать клиентам.  Второй PDB\-файл будет содержать только следующее:  
  
-   открытые символы;  
  
-   список объектных файлов и частей исполняемого файла, к которым они относятся;  
  
-   Отладочные записи оптимизации указателя фрейма \(FPO\), используемые для прохода по стеку  
  
 Очищенный PDB\-файл не будет содержать следующее:  
  
-   сведения о типе;  
  
-   сведения о номерах строк;  
  
-   символы CodeView, связанные с объектными файлами, например символы CodeView для функций, локальных и статических данных  
  
 Полный PDB\-файл по\-прежнему будет создаваться при использовании параметра \/PDBSTRIPPED.  
  
 Если PDB\-файл не создается, то параметр \/PDBSTRIPPED игнорируется.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Отладка**.  
  
4.  Измените свойство **Удалять закрытые символы**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)