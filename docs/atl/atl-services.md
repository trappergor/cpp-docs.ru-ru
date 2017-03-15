---
title: "Службы ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "службы ATL"
  - "COM-объекты, ATL - библиотека"
  - "CServiceModule - класс"
  - "службы, ATL - библиотека"
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Службы ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создание com\-объектов библиотеки ATL таким образом, чтобы он выполняется в службе, просто используйте вкладку служба \(EXE\) из списка параметров сервера в мастере проекта библиотеки ATL.  После этого мастер создает класс, производный от `CAtlServiceModuleT` для реализации службы.  
  
 Если COM\-объект библиотеки ATL будет создано в качестве службы, она просто будет зарегистрирован как локальный сервер, и оно не будет отображаться в списке служб на Панели управления.  Это происходит потому, что проще отладку службы, как локальный сервер не как служба.  Чтобы установить его как служба, выполните следующую команду в командной строке:  
  
 `YourEXE` `.exe /Service`  
  
 Чтобы удалить его, выполните следующие действия:  
  
 `YourEXE` `.exe /UnregServer`  
  
 Первые 4 в подразделах этого раздела описываются действия, которые происходят во время выполнения функции\-члены `CAtlServiceModuleT`.  В этих разделах представлены в той же последовательности, что и функциям обычно вызывают.  Чтобы улучшить ваше понимание этих разделах рекомендуется использовать исходный код, созданный мастером проекта библиотеки ATL в качестве ссылки.  Эти первые 4 разделах:  
  
-   [Функция CAtlServiceModuleT::Start](../atl/catlservicemodulet-start-function.md)  
  
-   [Функция CAtlServiceModuleT::ServiceMain](../atl/catlservicemodulet-servicemain-function.md)  
  
-   [Функция CAtlServiceModuleT::Run](../atl/catlservicemodulet-run-function.md)  
  
-   [Функция CAtlServiceModuleT::Handler](../Topic/CAtlServiceModuleT::Handler%20Function.md)  
  
 3 Последних разделах рассматриваются понятия, относящиеся к разработке службы:  
  
-   [записи реестра](../atl/registry-entries.md) для служб библиотека ATL  
  
-   [DCOMCNFG](../Topic/DCOMCNFG.md)  
  
-   [Советы по отладке](../atl/debugging-tips.md) для служб библиотека ATL  
  
## См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)