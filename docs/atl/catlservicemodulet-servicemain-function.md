---
title: Функция CAtlServiceModuleT::ServiceMain
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 81cd8fcbdf275063b243e215301eff504a2b5cc6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223213"
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
