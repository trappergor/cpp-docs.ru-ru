---
title: Функция CAtlServiceModuleT::Run | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e509ad88a744f6ebaaca41ecd0d6455d68c2585c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850658"
---
# <a name="catlservicemoduletrun-function"></a>Функция CAtlServiceModuleT::Run
`Run` содержит вызовы `PreMessageLoop`, `RunMessageLoop`, и `PostMessageLoop`. После вызова, `PreMessageLoop` сначала сохраняет идентификатор потока службы. Служба будет использовать этот идентификатор, чтобы завершить свою работу, отправляя сообщение WM_QUIT с помощью функции Win32 API, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` затем вызывает `InitializeSecurity`. По умолчанию `InitializeSecurity` вызовы [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) с дескриптором безопасности, присваивается значение NULL, означающее, что любой пользователь имеет доступ к объекту.  
  
 Если вы не хотите, чтобы службы, чтобы указать собственный уровень безопасности, переопределить `PreMessageLoop` и не вызывайте `InitializeSecurity`, и затем COM определяет параметры безопасности из реестра. Настройка параметров реестра удобно с [DCOMCNFG](../atl/dcomcnfg.md) служебная программа, описанных в этом разделе.  
  
 После указания безопасности с помощью COM зарегистрирован объект таким образом, чтобы новые клиенты могут подключаться к программе. Наконец программа сообщает диспетчер управления службами (SCM), что он работает, и программа переходит в цикл обработки сообщений. Программа продолжает работать, пока она отправляет сообщение quit при завершении работы службы.  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)   
 [Класс CSecurityDesc](../atl/reference/csecuritydesc-class.md)   
 [Класс CSid](../atl/reference/csid-class.md)   
 [Класс CDacl](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)

