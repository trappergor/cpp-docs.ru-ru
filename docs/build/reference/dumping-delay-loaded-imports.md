---
title: "Сохранение отложенно загружаемых импортированных элементов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "импорты, загружаемые с задержкой"
  - "импорты, загружаемые с задержкой, дамп"
  - "импорты (загружаемые с задержкой)"
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Сохранение отложенно загружаемых импортированных элементов
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отложенно загружаемые импортированные элементы можно сохранять с помощью [dumpbin \/imports](../../build/reference/imports-dumpbin.md) и просматривать со сведениями, несколько отличающимися от обычных импортируемых элементов.  Они находятся в отдельном разделе \/imports dumping и явно помечены как отложенно загружаемые импортируемые элементы.  Если в образе имеется информация о загрузке, то это также отмечается.  Если имеется информация о привязке, ставится отметка времени \/ даты целевой DLL, а также связанные адреса импортированных элементов.  
  
## См. также  
 [Поддержка компоновщика для DLLs, загружаемых с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)