---
title: "/NOLOGO (отмена вывода начального заголовка) (Компоновщик) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.SuppressStartupBanner"
  - "/nologo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOLOGO - параметр компоновщика"
  - "баннеры, отключение при загрузке"
  - "сообщение об авторских правах"
  - "NOLOGO параметр компоновщика"
  - "-NOLOGO параметр компоновщика"
  - "отмена вывода начального заголовка - параметр компоновщика"
  - "номера версий, вывод компоновщика - запрещение"
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NOLOGO (отмена вывода начального заголовка) (Компоновщик)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOLOGO  
```  
  
## Заметки  
 Параметр \/NOLOGO запрещает отображение сообщения об авторском праве и номера версии.  
  
 Этот параметр также подавляет вывод из командных файлов.  Дополнительные сведения см. в разделе [Командные файлы LINK](../../build/reference/link-command-files.md).  
  
 По умолчанию эта информация передается компоновщиком в окно вывода.  В командной строке она отправляется в стандартный вывод и может быть перенаправлена в файл.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Этот параметр должен использоваться только в командной строке.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  Этот параметр компоновщика нельзя изменить программным способом.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)