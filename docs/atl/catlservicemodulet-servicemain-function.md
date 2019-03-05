---
title: Функция CAtlServiceModuleT::ServiceMain
ms.date: 11/04/2016
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 32bdea1eb39c91ddb58def72bd16acc2f16ab936
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295429"
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
