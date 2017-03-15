---
title: "/WINMD (создавать метаданные Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadata"
dev_langs: 
  - "C++"
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /WINMD (создавать метаданные Windows)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обеспечивает создание файла метаданных среды выполнения Windows \(.winmd\).  
  
```  
  
/WINMD[:{NO|ONLY}]  
```  
  
## Заметки  
 \/WINMD  
 Параметр по умолчанию для приложений [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Компоновщик создает и бинарный исполняемый файл и файл метаданных .winmd.  
  
 \/WINMD:NO  
 Компоновщик создает только бинарный исполняемый файл, но не .winmd файл.  
  
 \/WINMD:ONLY  
 Компоновщик создает только файл .winmd, но не бинарный исполняемый файл.  
  
 По умолчанию имя файла вывода имеет форму `binaryname`.winmd.  Чтобы задать другое имя файла, используйте параметр [\/WINMDFILE](../Topic/-WINMDFILE%20\(Specify%20winmd%20File\).md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Метаданные Windows**.  
  
4.  В раскрывающемся списке **Создавать метаданные Windows** выберите параметр требуется.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)