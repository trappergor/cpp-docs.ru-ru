---
title: "Общие принципы разработки классов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы [C++], конструктор классов MFC"
  - "разработка классов"
  - "MFC [C++], API Windows"
  - "Visual C, Вызовы API Windows"
  - "Windows API [C++], и MFC"
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Общие принципы разработки классов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Windows предусматривает перед язык C\+\+ стал популярным.  Поскольку тысячи приложения используют программный интерфейс \(API\) Windows\-приложение языка C\#, этот интерфейс будет поддерживаться для обозримое будущее.  Любой интерфейс Windows C\+\+, поэтому построение поверх процедурного API языка C\#.  Это гарантирует, что приложение C\+\+ будут сосуществовать с приложениями C.  
  
 Библиотеки Microsoft Foundation Class объектно\-ориентированного интерфейса в Windows, соответствующих следующих целей разработки:  
  
-   В усилии значительно приоритета для создания приложения Windows.  
  
-   Скорость выполнения эквивалентна параметрам API языка C\#.  
  
-   Минимальная нагрузка размера кода.  
  
-   Возможность вызова любая функция C Windows напрямую.  
  
-   Более простое преобразование существующих приложений C в C\+\+.  
  
-   Возможность использования существующей базы Windows C\# языка программирования взаимодействие.  
  
-   Более легко использовать API Windows с C\+\+ с C.  
  
-   Область для использования, но мощные абстракции осложненных функции, такие как элементы управления ActiveX, поддержка баз данных, печать, панели инструментов и строки состояния.  
  
-   True API Windows для C\+\+ эффективно использует функции языка C C\+\+.  
  
 Дополнительные по разработке библиотеки MFC см. в следующих разделах:  
  
-   [Приложение .NET](../mfc/application-framework.md)  
  
-   [Связь с API языка C.](../mfc/relationship-to-the-c-language-api.md)  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)