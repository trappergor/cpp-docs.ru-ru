---
title: "/WINMDKEYCONTAINER (указать контейнер ключей) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDKEYCONTAINER"
dev_langs: 
  - "C++"
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDKEYCONTAINER (указать контейнер ключей)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает контейнер ключа для подписывания файла метаданных Windows \(.winmd\).  
  
```  
  
/WINMDKEYCONTAINER:name  
  
```  
  
## Заметки  
 Напоминает параметр компоновщика [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md), применен к файлу a \(.winmd\).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Метаданные Windows**.  
  
4.  В поле **Контейнер ключа метаданных Windows** введите расположение.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)