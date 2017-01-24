---
title: "/FORCE (Назначенный файл вывода) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ForceLink"
  - "/force"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FORCE - параметр компоновщика"
  - "выходной файл (компоновщик)"
  - "FORCE - параметр компоновщика"
  - "-FORCE - параметр компоновщика"
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FORCE (Назначенный файл вывода)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## Заметки  
 Параметр \/FORCE указывает линковщику создать exe\- или DLL\-файл, даже если символ, на который ссылаются, не определен или множественно определен.  
  
 Параметр \/FORCE может получать необязательный аргумент:  
  
-   Использовать параметр \/FORCE:MULTIPLE для создания выходного файла, независимо от того, найдет параметр LINK несколько определений символа или нет.  
  
-   Использовать параметр \/FORCE:UNRESOLVED для создания выходного файла, независимо от того, найдет параметр LINK неопределенный символ или нет. Параметр \/FORCE:UNRESOLVED пропускается, если символ точки записи неразрешен.  
  
 Параметр \/FORCE без аргументов выражает как многократные, так и неразрешенные ссылки.  
  
 Файл, созданный при помощи этого параметра не может запуститься, как ожидалось.  Линковщик не компонует инкрементно, если указан параметр \/FORCE.  
  
 Если модуль скомпилирован при помощи **\/clr**, **\/FORCE** не создаст изображение.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметр в поле **Дополнительные параметры**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)