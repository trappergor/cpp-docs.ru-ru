---
title: "Функция CAtlServiceModuleT::Run | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ff3efe9298b7a2c11e7f83ef58640b2947519b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletrun-function"></a>Функция CAtlServiceModuleT::Run
**Запустите** содержит вызовы `PreMessageLoop`, `RunMessageLoop`, и `PostMessageLoop`. После вызова, `PreMessageLoop` сначала сохраняет идентификатор потока службы. Служба будет использовать этот идентификатор для закрытия, отправляя **WM_QUIT** сообщений с помощью функции API-интерфейса Win32, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop`Затем вызывается `InitializeSecurity`. По умолчанию `InitializeSecurity` вызовы [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) дескриптор безопасности, присваивается значение NULL, означающее, что любой пользователь имеет доступ к данным объектом.  
  
 Если не требуется, чтобы службы, чтобы указать собственный уровень безопасности, переопределить `PreMessageLoop` и не вызывайте `InitializeSecurity`, и затем COM определяет параметры безопасности из реестра. Для настройки параметров реестра удобно с [DCOMCNFG](../atl/dcomcnfg.md) программа описано далее в этом разделе.  
  
 После безопасности объект зарегистрирован с помощью COM, чтобы новые клиенты могли подключаться к программе. Наконец программа сообщает диспетчера управления службами (SCM), что он работает, и программа вводит цикл обработки сообщений. Программа продолжает выполняться, пока он отправляет сообщение о выходе при завершении работы службы.  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)   
 [Класс CSecurityDesc](../atl/reference/csecuritydesc-class.md)   
 [Класс CSid](../atl/reference/csid-class.md)   
 [Класс CDacl](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)

