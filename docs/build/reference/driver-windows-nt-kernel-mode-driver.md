---
title: "/DRIVER (драйвер режима ядра Windows NT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.driver"
  - "/driver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DRIVER - параметр компоновщика"
  - "DRIVER - параметр компоновщика"
  - "-DRIVER - параметр компоновщика"
  - "драйвер, работающий в режиме ядра"
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /DRIVER (драйвер режима ядра Windows NT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DRIVER[:UPONLY | :WDM]  
```  
  
## Заметки  
 Использовать параметр компоновщика \/DRIVER для построения драйвера в режиме ядра Windows NT.  
  
 При использовании **\/DRIVER:UPONLY** компоновщик добавляет битовый флаг **IMAGE\_FILE\_UP\_SYSTEM\_ONLY** к атрибутам выходного заголовка для указания на то, что это однопроцессорный драйвер.  Операционная система отклонит загрузку UP\-драйвера в многопроцессорной \(MP\) системе.  
  
 При использовании **\/DRIVER:WDM** компоновщик устанавливает битовый флаг **IMAGE\_DLLCHARACTERISTICS\_WDM\_DRIVER** в поле DllCharacteristics дополнительного заголовка.  
  
 Если параметр **\/DRIVER** не указан, эти битовые флаги не устанавливаются компоновщиком.  
  
 Если параметр **\/DRIVER** указан, происходит следующее.  
  
-   Действует параметр \/FIXED:NO \([\/FIXED \(фиксированный базовый адрес\)](../../build/reference/fixed-fixed-base-address.md)\).  
  
-   Выходной файл получает расширение .sys  Для изменения имени файла и расширения по умолчанию используется параметр **\/OUT** \([\/OUT \(имя выходного файла\)](../../build/reference/out-output-file-name.md)\).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Система**.  
  
4.  Измените значение свойства **Драйвер**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел `P:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.driver`.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)