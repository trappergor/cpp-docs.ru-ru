---
title: "/NOENTRY (точка входа отсутствует) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ResourceOnlyDLL"
  - "/noentry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOENTRY - параметр компоновщика [C++]"
  - "DLL-библиотеки [C++], создание"
  - "точки входа [C++], определение компоновщика"
  - "NOENTRY - параметр компоновщика"
  - "-NOENTRY - параметр компоновщика"
  - "библиотеки DLL, содержащие только ресурсы [C++], создание"
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NOENTRY (точка входа отсутствует)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOENTRY  
```  
  
## Заметки  
 Параметр \/NOENTRY требуется для создания DLL\-библиотеки, содержащей только ресурсы, без исполняемого кода.  Для получения дополнительной информации см. [Создание библиотек DLL, содержащих только ресурсы](../../build/creating-a-resource-only-dll.md).  
  
 Используйте этот параметр, чтобы LINK не добавлял ссылку на `_main` в DLL.  
  
### Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Дополнительно**.  
  
4.  Измените свойство **Не точка входа**.  
  
### Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.  
  
## См. также  
 [Создание библиотек DLL, содержащих только ресурсы](../../build/creating-a-resource-only-dll.md)   
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)