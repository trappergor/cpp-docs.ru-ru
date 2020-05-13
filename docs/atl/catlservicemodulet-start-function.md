---
title: CAtlServiceModuleT::Функция запуска
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 50054bbb34bcc31a1d11dd8bfab797f98e4e82f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317281"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT::Функция запуска

Когда служба `_tWinMain` запущена, `CAtlServiceModuleT::WinMain`звонки, которые `CAtlServiceModuleT::Start`в свою очередь звонки .

`CAtlServiceModuleT::Start`настраивает массив `SERVICE_TABLE_ENTRY` структур, которые отображают каждую службу с функцией запуска. Затем этот массив передается функции API Win32, [StartServiceCtrlDispatcher.](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw) Теоретически один EXE может обрабатывать несколько служб, `SERVICE_TABLE_ENTRY` а массив может иметь несколько структур. В настоящее время, однако, ATL-сервис поддерживает только одну услугу на EXE. Таким образом, массив имеет одну запись, `_ServiceMain` которая содержит имя службы и функцию запуска. `_ServiceMain`является статичной `CAtlServiceModuleT` функцией члена, которая вызывает `ServiceMain`нестатичную функцию члена, .

> [!NOTE]
> `StartServiceCtrlDispatcher` Неподключение к менеджеру управления службой (SCM), вероятно, означает, что программа не работает как служба. В этом случае программа `CAtlServiceModuleT::Run` вызывает непосредственно так, что программа может работать как локальный сервер. Для получения дополнительной информации о запуске [Debugging Tips](../atl/debugging-tips.md)программы в качестве локального сервера см.

## <a name="see-also"></a>См. также раздел

[Службы](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Начало](../atl/reference/catlservicemodulet-class.md#start)
