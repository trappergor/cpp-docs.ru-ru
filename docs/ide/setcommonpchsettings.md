---
title: "SetCommonPchSettings | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetCommonPchSettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommonPchSettings - метод"
ms.assetid: 12f5524b-f654-4222-b979-8ee0d9f58c14
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# SetCommonPchSettings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Устанавливает параметры предкомпилированных заголовков для проекта.  
  
## Синтаксис  
  
```  
  
      function SetCommonPchSettings(   
   oProj    
);  
```  
  
#### Параметры  
 `oProj`  
 Выбранный проект.  
  
## Заметки  
 Эта функция вызывается для установки параметров предкомпилированных заголовков в проекте.  
  
 Эта функция устанавливает для свойства <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A> следующие значения:  
  
-   **pchUseUsingSpecific** Использует параметр компилятора [\/Yu \(использовать файл предкомпилированного заголовка\)](../build/reference/yu-use-precompiled-header-file.md).  
  
-   **pchCreateUsingSpecific** Использует параметр компилятора [\/Yu \(создать файл предкомпилированного заголовка\)](../build/reference/yc-create-precompiled-header-file.md).  
  
## Пример  
  
```  
if ((strAppType == "LIB" || ((strAppType == "CONSOLE") &&   
   wizard.FindSymbol(SUPPORT_MFC"))) && !Pch)  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetNoCommonPchSettings(selProj);  
   }  
else  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetcommonPchSettings(selProj);  
   }  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [SetNoPchSettings](../ide/setnopchsettings.md)   
 [AddCommonConfig](../ide/addcommonconfig.md)