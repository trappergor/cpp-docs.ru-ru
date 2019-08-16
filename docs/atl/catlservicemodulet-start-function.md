---
title: 'Функция функция CAtlServiceModuleT:: Start'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: e6de15f40e89bfffba504db04ee7a16b2a68cac9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491668"
---
# <a name="catlservicemoduletstart-function"></a>Функция функция CAtlServiceModuleT:: Start

При запуске `_tWinMain` службы вызывает метод `CAtlServiceModuleT::WinMain`, который, в свою очередь, `CAtlServiceModuleT::Start`вызывает.

`CAtlServiceModuleT::Start`настраивает массив `SERVICE_TABLE_ENTRY` структур, которые сопоставляют каждую службу с ее функцией запуска. Затем этот массив передается в функцию API Win32 [сбой StartServiceCtrlDispatcher](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw). Теоретически один исполняемый файл может работать с несколькими службами, и массив может иметь `SERVICE_TABLE_ENTRY` несколько структур. Однако в настоящее время служба, созданная библиотекой ATL, поддерживает только одну службу на каждый исполняемый файл. Таким образом, массив содержит одну запись, которая содержит имя службы и `_ServiceMain` функцию Startup. `_ServiceMain`— Это статическая функция `CAtlServiceModuleT` -член, которая вызывает нестатичную функцию-член,. `ServiceMain`

> [!NOTE]
>  `StartServiceCtrlDispatcher` Сбой подключения к диспетчеру управления службами (SCM), вероятно, означает, что программа не запущена как служба. В этом случае программа вызывает `CAtlServiceModuleT::Run` напрямую, чтобы программа могла работать как локальный сервер. Дополнительные сведения о запуске программы в качестве локального сервера см. в разделе [Советы по отладке](../atl/debugging-tips.md).

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[Функция CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#start)
