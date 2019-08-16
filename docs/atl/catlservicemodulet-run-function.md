---
title: 'Функция функция CAtlServiceModuleT:: Run'
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: 0c35020996852731a8f22c15860d4cceb7a8bdb6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491520"
---
# <a name="catlservicemoduletrun-function"></a>Функция функция CAtlServiceModuleT:: Run

`Run`содержит вызовы `PreMessageLoop`, `RunMessageLoop`и. `PostMessageLoop` После вызова `PreMessageLoop` сначала сохраняет идентификатор потока службы. Служба будет использовать этот идентификатор для закрытия, отправив сообщение WM_QUIT с помощью функции API Win32, [постсреадмессаже](/windows/win32/api/winuser/nf-winuser-postthreadmessagew).

`PreMessageLoop`затем вызывает `InitializeSecurity`метод. По умолчанию `InitializeSecurity` вызывает [CoInitializeSecurity](/windows/win32/api/combaseapi/nf-combaseapi-coinitializesecurity) с дескриптором безопасности со значением NULL, что означает, что любой пользователь имеет доступ к вашему объекту.

Если вы не хотите, чтобы служба определяла собственную безопасность, переопределите `PreMessageLoop` и не вызывает `InitializeSecurity`, а com определит параметры безопасности из реестра. Для настройки параметров реестра удобно использовать служебную программу [DCOMCNFG](../atl/dcomcnfg.md) , которая обсуждается далее в этом разделе.

После указания безопасности объект регистрируется в COM, чтобы новые клиенты могли подключаться к программе. Наконец, программа сообщает диспетчеру управления службами, что он работает, а программа входит в цикл обработки сообщений. Программа продолжает работать до тех пор, пока не будет отправлено сообщение о выходе после завершения работы службы.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[Класс CSecurityDesc](../atl/reference/csecuritydesc-class.md)<br/>
[Класс CSid](../atl/reference/csid-class.md)<br/>
[Класс CDacl](../atl/reference/cdacl-class.md)<br/>
[Функция CAtlServiceModuleT:: Run](../atl/reference/catlservicemodulet-class.md#run)
