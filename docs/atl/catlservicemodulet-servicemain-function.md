---
title: Функция CAtlServiceModuleT::ServiceMain | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs:
- C++
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae357caad88e128fe9f3742887781d0096efe2c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058592"
---
# <a name="catlservicemoduletservicemain-function"></a>Функция CAtlServiceModuleT::ServiceMain

Диспетчер управления службами (SCM) вызывает `ServiceMain` при открытии приложения службы на панели управления, выберите службу и нажмите кнопку **запустить**.

После SCM вызывает `ServiceMain`, службы необходимо предоставить диспетчер управления Службами функцию обработчика событий. Эта функция позволяет диспетчера управления Службами для получения сведений о состоянии службы и передать конкретные инструкции (например, приостановка или остановка). Диспетчер управления Службами получает эту функцию, когда служба передает `_Handler` функции Win32 API, [RegisterServiceCtrlHandler](/windows/desktop/api/winsvc/nf-winsvc-registerservicectrlhandlera). (`_Handler` является статической функции-члене, вызывающая функцию-член [обработчик](../atl/reference/catlservicemodulet-class.md#handler).)

Во время запуска службы также сообщает о его текущее состояние диспетчера управления Службами. Это достигается путем передачи SERVICE_START_PENDING функции Win32 API, [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).

`ServiceMain` затем вызывает `CAtlExeModuleT::InitializeCom`, который вызывает функцию интерфейса API Win32 [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex). По умолчанию `InitializeCom` передает флаг COINIT_MULTITHREADED функции. Этот флаг указывает, что она является свободным сервером.

Теперь `CAtlServiceModuleT::Run` вызывается для выполнения основной рабочей службы. `Run` продолжает выполняться до остановки службы.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

