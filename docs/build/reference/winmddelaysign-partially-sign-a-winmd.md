---
title: "/WINMDDELAYSIGN (частично подпишите файл winmd) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDDelaySign"
dev_langs: 
  - "C++"
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDDELAYSIGN (частично подпишите файл winmd)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Включает частично подпись файла метаданных среды выполнения Windows \(.winmd\) путем помещения открытого ключа в файл.  
  
```  
  
/WINMDDELAYSIGN[:NO]  
  
```  
  
## Заметки  
 Напоминает параметр компоновщика [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), применен к файлу .winmd.  Используйте **\/WINMDDELAYSIGN**, если требуется помещать только открытый ключ в файл .winmd.  По умолчанию если компоновщик выполняет **\/WINMDDELAYSIGN:NO** задано; иными словами, он не подписываются файл winmd.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Метаданные Windows**.  
  
4.  В раскрывающемся списке **Отложенное подписание метаданных Windows** выберите параметр требуется.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)