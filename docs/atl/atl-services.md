---
title: "Службы ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule
dev_langs:
- C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d13eebbe96ba57c82e3bf1c360b0cb471a6bd975
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-services"></a>Службы ATL
Чтобы создать ATL COM-объекта, чтобы он запускался в службе, просто выберите службы (EXE) из списка параметров мастер проектов ATL server. Мастер создаст класс, производный от `CAtlServiceModuleT` для реализации службы.  
  
 При построении объекта ATL COM как служба будет регистрироваться только как локальный сервер и он не будет отображаться в списке служб на панели управления. Это, так как это упрощает отладку службы, что локальный сервер как служба. Чтобы установить его в качестве службы, выполните следующую команду командной строке:  
  
 `YourEXE` `.exe /Service`  
  
 Чтобы удалить его, выполните следующую команду:  
  
 `YourEXE` `.exe /UnregServer`  
  
 Первые четыре темы в этом разделе рассматриваются действия, которые выполняются во время выполнения `CAtlServiceModuleT` функции-члены. Эти разделы отображаются в той же последовательности, как функции обычно вызываются. Чтобы улучшить понимание этих разделов, рекомендуется использовать исходный код, созданный мастером проекта ATL как ссылка. Эти первые четыре относятся следующие.  
  

-   [Функция CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)  
  
-   [Функция CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)  
  
-   [Функция CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)  
  
-   [Функция CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)  
  
 В последних трех разделах рассматриваются основные понятия, относящиеся к разработке службы:  
  
-   [Записи реестра](../atl/registry-entries.md) для службы ATL  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [Советы по отладке](../atl/debugging-tips.md) для службы ATL  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

