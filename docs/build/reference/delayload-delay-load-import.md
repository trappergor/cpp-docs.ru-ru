---
title: "/DELAYLOAD (загрузка импорта с задержкой) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delayload"
  - "VC.Project.VCLinkerTool.DelayLoadDLLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYLOAD - параметр компоновщика"
  - "отложенная загрузка библиотек DLL, /DELAYLOAD - параметр"
  - "DELAYLOAD - параметр компоновщика"
  - "-DELAYLOAD - параметр компоновщика"
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /DELAYLOAD (загрузка импорта с задержкой)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYLOAD:dllname  
  
```  
  
## Параметры  
 `dllname`  
 Имя DLL\-библиотеки, загрузку которой нужно задержать.  
  
## Заметки  
 При использовании параметра \/DELAYLOAD DLL\-библиотека, указанная с помощью `dllname`, загружается только при первом вызове функции этой DLL\-библиотеки программой.  Для получения дополнительной информации см. [Поддержка компоновщика для DLLs, загружаемых с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md).  Можно использовать этот параметр сколько угодно раз, указывая сколько угодно DLL\-библиотек.  При компоновке программы нужно использовать Delayimp.lib. Также можно использовать собственную вспомогательную функцию загрузки с задержкой.  
  
 Параметр [\/DELAY](../../build/reference/delay-delay-load-import-settings.md) указывает настройки привязки и загрузки для всех загружаемых с задержкой DLL\-библиотек.  
  
### Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  В папке **Компоновщик** выберите страницу свойств **Ввод**.  
  
3.  Измените свойство **DLL, загружаемые с задержкой**.  
  
### Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)