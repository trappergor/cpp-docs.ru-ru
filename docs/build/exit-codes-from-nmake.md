---
title: "Коды выхода из NMAKE | Microsoft Docs"
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
helpviewer_keywords: 
  - "коды завершения"
  - "программа NMAKE, коды завершения"
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Коды выхода из NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Программа NMAKE возвращает следующие коды выхода:  
  
|Код|Значение|  
|---------|--------------|  
|0|Нет ошибок \(возможно предупреждение\)|  
|1|Не завершен процесс построения \(возвращается только при использовании параметра \/K\)|  
|2|Ошибка программы, связанная с одной из следующих ситуаций:|  
||-   Синтаксическая ошибка в файле makefile|  
||-   Ошибка или код выхода из команды|  
||-   Прерывание со стороны пользователя|  
|4|Системная ошибка — недостаточно памяти|  
|255|Устаревший целевой объект \(возвращается только при использовании параметра \/Q\)|  
  
## См. также  
 [Запуск программы NMAKE](../build/running-nmake.md)