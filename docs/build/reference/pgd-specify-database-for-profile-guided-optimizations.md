---
title: "/PGD (указание базы данных для профильной оптимизации) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ProfileGuidedDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PGD - параметр компоновщика"
  - "-PGD - параметр компоновщика"
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /PGD (указание базы данных для профильной оптимизации)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/PGD:`filename`  
  
## Заметки  
 Здесь:  
  
 `filename`  
 Имя PGD\-файла, который будет использоваться для хранения сведений о выполняемой программе.  
  
## Заметки  
 Параметр \/PGD следует использовать вместе с параметром [\/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md), чтобы указать имя или расположение PGD\-файла, отличное от установленного по умолчанию.  Если параметр \/PGD не указан, то PDB\-файл будет создан в том же каталоге, что и выходной файл \(с расширением EXE или DLL\), и с тем же самым именем, что и у выходного файла.  
  
 Если указан параметр \/LTCG:PGOPTIMIZE, с помощью \/PGD следует указать имя PGD\-файла, который должен использоваться для создания оптимизированного образа.  
  
 Дополнительные сведения см. в разделе [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Оптимизация**.  
  
5.  Измените свойство **База данных профильной оптимизации**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)