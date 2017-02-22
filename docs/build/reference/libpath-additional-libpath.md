---
title: "Параметр /LIBPATH (дополнительный параметр libpath) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/libpath"
  - "VC.Project.VCLinkerTool.AdditionalLibraryDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LIBPATH - параметр компоновщика"
  - "Дополнительный путь к библиотеке - параметр компоновщика"
  - "библиотека среды - переопределение пути"
  - "LIBPATH - параметр компоновщика"
  - "-LIBPATH - параметр компоновщика"
  - "путь к библиотеке - параметр компоновщика"
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Параметр /LIBPATH (дополнительный параметр libpath)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LIBPATH:dir  
```  
  
## Заметки  
 Здесь:  
  
 `dir`  
 Путь, по которому компоновщик выполняет поиск перед поиском по пути, указанному в параметре среды LIB.  
  
## Заметки  
 Параметр \/LIBPATH предназначен для переопределения пути к библиотеке среды.  Сначала компоновщик выполняет поиск по указанному в этом параметре пути, а затем — по пути, указанному в переменной среды LIB.  Для каждого вводимого параметра \/LIBPATH можно указать только один каталог.  Чтобы задать несколько каталогов, используйте соответствующее число параметров \/LIBPATH.  Порядок определения каталогов задает порядок поиска в них.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Щелкните страницу свойств **Общие**.  
  
4.  Измените значение свойства **Дополнительные каталоги библиотек**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)