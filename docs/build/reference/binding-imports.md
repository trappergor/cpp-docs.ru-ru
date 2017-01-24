---
title: "Связывание Imports | Microsoft Docs"
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
  - "/DELAY:NOBIND - параметр компоновщика"
  - "DELAY:NOBIND - параметр компоновщика"
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Связывание Imports
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поведение компоновщика по умолчанию – это создание связанной таблицы адресов импорта для DLL, загружаемых с задержкой.  Если библиотека DLL привязана, то вспомогательная функция будет пытаться использовать данные привязки вместо вызова функции **GetProcAddress** для каждого из импортов, на который обнаруживается ссылка.  Если либо временная метка, либо основной адрес не соответствуют метке и адресу загружаемой библиотеки DLL, вспомогательная функция будет предполагать, что связанная таблица адресов импорта является устаревшей и будет работать так, как будто она не существует.  
  
 Если не требуется привязать импорты DLL, загружаемые с задержкой, указание [\/delay](../../build/reference/delay-delay-load-import-settings.md):nobind в командной строке компоновщика будет запрещать связанной таблице адресов импорта генерировать и потреблять место в файле образа.  
  
## См. также  
 [Поддержка компоновщика для DLLs, загружаемых с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)