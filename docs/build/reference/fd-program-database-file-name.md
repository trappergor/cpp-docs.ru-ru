---
title: "/Fd (имя файла базы данных программы) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName"
  - "VC.Project.VCCLCompilerTool.ProgramDataBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PDB-файлы, создание"
  - "/FD - параметр компилятора [C++]"
  - "FD - параметр компилятора [C++]"
  - "-FD - параметр компилятора [C++]"
  - "PDB-файлы, создание"
  - "база данных программы - параметр компилятора [C++]"
  - "имя файла базы данных программы[C++]"
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Fd (имя файла базы данных программы)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает имя файла базы данных программы \(PDB\), созданного при помощи параметров [\/Z7, \/Zi, \/ZI \(формат отладочной информации\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).  
  
## Синтаксис  
  
```  
/Fdpathname  
```  
  
## Заметки  
 Если не использовать параметр **\/Fd**, по умолчанию PDB\-файл получит имя VC`x`0.pdb, где `x` — это основной номер используемой версии Visual C\+\+.  
  
 При указании пути, который не включает имя файла \(путь выполнения в обратной косой чертой\), компилятор создает pdb\-файл с именем VC `x`0.pdb в указанном каталоге.  
  
 Если имя файла указано без расширения, то компилятор использует расширение PDB.  
  
 Этот параметр также служит для задания имени файла состояния \(IDB\), используемого для минимального перепостроения и инкрементной компиляции.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Выходные файлы**.  
  
4.  Измените значение свойства **Имя файла базы данных программы**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.  
  
## Пример  
 Использование следующей командной строки приведет к созданию PDB\-файла с именем PROG.pdb и IDB\-файла с именем PROG.idb:  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## См. также  
 [Параметры выходного файла \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [Указание пути](../Topic/Specifying%20the%20Pathname.md)