---
title: "/FR, /Fr (создать SBR-файл) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.BrowseInformation"
  - "VC.Project.VCCLCompilerTool.BrowseInformation"
  - "/fr"
  - "VC.Project.VCCLCompilerTool.BrowseInformationFile"
  - "VC.Project.VCCLWCECompilerTool.BrowseInformationFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FR - параметр компилятора [C++]"
  - "FR - параметр компилятора [C++]"
  - "-FR - параметр компилятора [C++]"
  - "символы браузера - информация"
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FR, /Fr (создать SBR-файл)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает SBR\-файлы.  
  
## Синтаксис  
  
```  
/FR[pathname[\filename]]  
/Fr[pathname[\filename]]  
```  
  
## Заметки  
 В процессе сборки программа обслуживания файлов информации об исходном коде Майкрософт \(BSCMAKE\) использует эти файлы для создания BSC\-файла, с помощью которого отображается информация об исходном коде.  
  
 **\/FR** создает SBR\-файл с полными символьными данными.  
  
 **\/Fr** создает SBR\-файл без сведений о локальных переменных.  
  
 Если не указать `filename`, SBR\-файл получает такое же базовое имя, как у исходного файла.  
  
 Использовать параметр **\/Fr** не рекомендуется; используйте вместо него **\/FR**. Дополнительные сведения см. в разделе "Нерекомендуемые и удаленные параметры компилятора" статьи [Параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
> [!NOTE]
>  Не изменяйте расширение SBR. Программе BSCMAKE требуются промежуточные файлы с этим расширением.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  В области навигации выберите страницу свойств **C\/C\+\+**, **Информация об исходном коде**.  
  
3.  Измените свойство **Файл информации об исходном коде** или **Включить информацию об исходном коде**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>.  
  
## См. также  
 [Параметры выходного файла \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [Указание пути](../Topic/Specifying%20the%20Pathname.md)