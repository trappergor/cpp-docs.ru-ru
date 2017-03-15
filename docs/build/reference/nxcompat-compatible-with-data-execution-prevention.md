---
title: "/NXCOMPAT (совместимо с предотвращением исполнения данных (DEP)) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/NXCOMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NXCOMPAT - параметр компоновщика"
  - "NXCOMPAT - параметр компоновщика"
  - "-NXCOMPAT - параметр компоновщика"
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает на то, что исполняемый файл был проверен на совместимость с функцией предотвращения исполнения данных Windows.  
  
## Синтаксис  
  
```  
/NXCOMPAT[:NO]  
```  
  
## Заметки  
 По умолчанию параметр **\/NXCOMPAT** включен.  
  
 **\/NXCOMPAT:NO** может использоваться, чтобы явным образом определить исполняемый файл как не совместимый с функцией предотвращения исполнения данных.  
  
 Дополнительные сведения о предотвращении выполнения данных см. в следующих статьях:  
  
-   [Подробное описание функции \(DEP\) предотвращения выполнения данных](http://go.microsoft.com/fwlink/?LinkID=157771) на веб\-сайте центра справки и поддержки  
  
-   [Предотвращение выполнения данных](http://go.microsoft.com/fwlink/?LinkID=157770) веб\-сайта MSDN  
  
-   [Предотвращение выполнения типа данных \(Windows\)](http://go.microsoft.com/fwlink/?LinkID=157768) веб\-сайта MSDN  
  
### Установка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно проекта **Страницы свойств**.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметр в поле **Дополнительные параметры**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)