---
title: "Функция CAtlServiceModuleT::ServiceMain | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs:
- C++
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 633e9bc4689ced93e1c22151b32654f7ae9d7ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletservicemain-function"></a>Функция CAtlServiceModuleT::ServiceMain
Диспетчер управления службами (SCM) вызывает `ServiceMain` при открытии приложения службы на панели управления, выберите службу и нажмите кнопку **запустить**.  
  
 После SCM вызывает `ServiceMain`, службы необходимо предоставить SCM функцию обработчика событий. Эта функция позволяет SCM получения состояния службы и передачи специальные инструкции (например, приостановка или остановка). Диспетчер управления Службами получает эту функцию, если служба передает **_Handler** функции API-интерфейса Win32, [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054). (**_Handler** является статической функции-члене, вызывает функцию-член [обработчик](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 Во время запуска службы также сообщает о SCM его текущего состояния. Это делается путем передачи **SERVICE_START_PENDING** функции API-интерфейса Win32, [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain`затем вызывает `CAtlExeModuleT::InitializeCom`, который вызывает функции Win32 API [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279). По умолчанию `InitializeCom` передает **COINIT_MULTITHREADED** флаг функции. Этот флаг указывает, что она является сервером свободных потоков.  
  
 Теперь `CAtlServiceModuleT::Run` вызывается для выполнения основных работу службы. **Запустите** продолжает выполняться, пока служба остановлена.  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

