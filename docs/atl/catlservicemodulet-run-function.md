---
title: Функция CAtlServiceModuleT::Run
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: 0f50c13912bbfef861e8650ee7589daea1e45725
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250850"
---
# <a name="catlservicemoduletrun-function"></a>Функция CAtlServiceModuleT::Run

`Run` содержит вызовы `PreMessageLoop`, `RunMessageLoop`, и `PostMessageLoop`. После вызова, `PreMessageLoop` сначала сохраняет идентификатор потока службы. Служба будет использовать этот идентификатор, чтобы завершить свою работу, отправляя сообщение WM_QUIT с помощью функции Win32 API, [PostThreadMessage](/windows/desktop/api/winuser/nf-winuser-postthreadmessagea).

`PreMessageLoop` затем вызывает `InitializeSecurity`. По умолчанию `InitializeSecurity` вызовы [CoInitializeSecurity](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializesecurity) с дескриптором безопасности, присваивается значение NULL, означающее, что любой пользователь имеет доступ к объекту.

Если вы не хотите, чтобы службы, чтобы указать собственный уровень безопасности, переопределить `PreMessageLoop` и не вызывайте `InitializeSecurity`, и затем COM определяет параметры безопасности из реестра. Настройка параметров реестра удобно с [DCOMCNFG](../atl/dcomcnfg.md) служебная программа, описанных в этом разделе.

После указания безопасности с помощью COM зарегистрирован объект таким образом, чтобы новые клиенты могут подключаться к программе. Наконец программа сообщает диспетчер управления службами (SCM), что он работает, и программа переходит в цикл обработки сообщений. Программа продолжает работать, пока она отправляет сообщение quit при завершении работы службы.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[Класс CSecurityDesc](../atl/reference/csecuritydesc-class.md)<br/>
[Класс CSid](../atl/reference/csid-class.md)<br/>
[Класс CDacl](../atl/reference/cdacl-class.md)<br/>
[CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)
