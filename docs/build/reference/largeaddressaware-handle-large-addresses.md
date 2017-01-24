---
title: "/LARGEADDRESSAWARE (Обрабатывать большие адреса) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.LargeAddressAware"
  - "/largeaddressaware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LARGEADDRESSAWARE - параметр компоновщика"
  - "LARGEADDRESSAWARE - параметр компоновщика"
  - "-LARGEADDRESSAWARE - параметр компоновщика"
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LARGEADDRESSAWARE (Обрабатывать большие адреса)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## Заметки  
 Параметр \/LARGEADDRESSAWARE сообщает компоновщику, что приложение может обрабатывать адреса размером свыше 2 гигабайт.  В 64\-разрядных компиляторах этот параметр включен по умолчанию.  В 32\-разрядных компиляторах включен параметр \/LARGEADDRESSAWARE:NO, если в строке компоновщика для параметра \/LARGEADDRESSAWARE не указано иное.  
  
 Если компоновка приложения производилась с параметром \/LARGEADDRESSAWARE, использование параметра DUMPBIN [\/HEADERS](../../build/reference/headers.md) приведет к отображению соответствующих сведений.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Система**.  
  
4.  Измените свойство **Включить большие адреса**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)