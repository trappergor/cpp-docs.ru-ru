---
title: "Функция CAtlServiceModuleT::Handler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs: C++
helpviewer_keywords: Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00158bbed5318d919c284b91cd651141a35bd441
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemodulethandler-function"></a>Функция CAtlServiceModuleT::Handler
`CAtlServiceModuleT::Handler`является подпрограмму, которая вызывает диспетчер управления службами (SCM) для получения состояния службы и присвойте ему различные инструкции (например, остановка или приостановка). Диспетчер управления Службами передает код операции `Handler` для указания, что следует сделать. Службу создан ATL по умолчанию обрабатывает только инструкция stop. Если диспетчер управления Службами передает инструкция stop, службы показывает диспетчера управления Службами, программа собирается остановиться. После этого служба `PostThreadMessage` Чтобы отправить сообщение о выходе к самому себе. Это завершает цикл обработки сообщений и службы в конечном счете будет закрыт.  
  
 Чтобы обработать дополнительные инструкции, необходимо изменить `m_status` член данных инициализирован в `CAtlServiceModuleT` конструктора. Этот член данных сообщает SCM кнопки, которые следует включить при выборе службы в приложении службы на панели управления.  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

