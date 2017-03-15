---
title: "/I (дополнительные каталоги включения) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories"
  - "/I"
  - "VC.Project.VCNMakeTool.IncludeSearchPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/I - параметр компилятора [C++]"
  - "Дополнительные каталоги включения - параметр компилятора"
  - "I - параметр компилятора [C++]"
  - "-I - параметр компилятора [C++]"
  - "каталоги включений, параметр компилятора [C++]"
  - "установить каталоги включений"
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /I (дополнительные каталоги включения)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Добавляет каталог к списку каталогов для поиска включаемых файлов.  
  
## Синтаксис  
  
```  
/I[ ]directory  
```  
  
## Аргументы  
 `directory`  
 Каталог, добавляемый к списку каталогов для поиска включаемых файлов.  
  
## Заметки  
 Чтобы добавить несколько каталогов, используйте этот параметр несколько раз.  Поиск каталогов выполняется до тех пор, пока не найден указанный включаемый файл.  
  
 Этот параметр можно использовать с параметром пропуска стандартного пути включаемых файлов \([\/X \(Отклонение стандартных путей включения\)](../../build/reference/x-ignore-standard-include-paths.md)\).  
  
 Компилятор выполняет поиск каталогов в следующем порядке:  
  
1.  Каталог, содержащий исходный файл.  
  
2.  Каталоги, указанные с параметром **\/I**, в том порядке, в котором их находит CL.  
  
3.  Каталоги, указанные в переменной среды **INCLUDE**.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Общие**.  
  
4.  Измените свойство **Дополнительные каталоги включения**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.  
  
## Пример  
 Приведенная ниже команда выполняет поиск включаемых файлов, запрошенных файлом MAIN.c, в следующем порядке: сначала в каталоге, содержащем MAIN.c, затем в каталоге \\INCLUDE, затем в каталоге \\MY\\INCLUDE и, наконец, в каталогах, назначенных переменной среды INCLUDE.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)