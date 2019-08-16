---
title: 'Функция функция CAtlServiceModuleT:: ServiceMain'
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: b79767d4c1696174f90a325ea152ccc7939ed9fe
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491712"
---
# <a name="catlservicemoduletservicemain-function"></a>Функция функция CAtlServiceModuleT:: ServiceMain

Диспетчер управления службами вызывается `ServiceMain` при открытии приложения панели управления "службы", выборе службы и нажатии кнопки " **запустить**".

После вызова `ServiceMain`SCM служба должна предоставить SCM функцию обработчика. Эта функция позволяет SCM получать состояние службы и передавать конкретные инструкции (такие как приостановка или остановка). SCM получает эту функцию, когда служба передается `_Handler` в функцию API Win32, [регистерсервицектрлхандлер](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw). (`_Handler` — это статическая функция-член, которая вызывает [обработчик](../atl/reference/catlservicemodulet-class.md#handler)функции-члена, не являющейся статическим.)

При запуске служба также должна сообщать SCM о своем текущем состоянии. Это достигается путем передачи SERVICE_START_PENDING функции Win32 API [сбой SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus).

`ServiceMain`затем вызывает `CAtlExeModuleT::InitializeCom`метод, который вызывает функцию [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)интерфейса API Win32. По умолчанию `InitializeCom` передает флаг COINIT_MULTITHREADED в функцию. Этот флаг указывает, что программа является свободным потоком сервера.

`CAtlServiceModuleT::Run` Теперь вызывается для выполнения основной работы службы. `Run`будет выполняться до тех пор, пока служба не будет остановлена.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[Функция CAtlServiceModuleT:: ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
