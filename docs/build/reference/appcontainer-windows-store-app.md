---
title: "/APPCONTAINER (Приложение для Магазина Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /APPCONTAINER (Приложение для Магазина Windows)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, создает ли компоновщик исполняемый образ, который должен запускаться в контейнере приложения.  
  
## Синтаксис  
  
```  
/APPCONTAINER[:NO]  
```  
  
## Заметки  
 По умолчанию \/APPCONTAINER отключено.  
  
 Этот параметр изменяет исполняемый файл, чтобы указать, должно ли приложение выполняться в среде изоляции процессов appcontainer.  Задайте параметр \/APPCONTAINER для приложения, которое должно выполняться в среде appcontainer — например, приложения [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)]. \(Параметр задается автоматически в Visual Studio при создании приложения [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] из шаблона\). Для настольного приложения укажите \/APPCONTAINER:NO или просто опустив параметр.  
  
 Параметр \/APPCONTAINER впервые появился в [!INCLUDE[win8](../../build/includes/win8_md.md)].  
  
### Установка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно проекта **Страницы свойств**.  Для получения дополнительной информации см. [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Командная строка**.  
  
5.  В поле **Дополнительные параметры** введите `/APPCONTAINER` или `/APPCONTAINER:NO`.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)