---
title: Запуск программы как локального сервера
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: a412814fc5f3900a248f779501e2720b72287e57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196526"
---
# <a name="running-the-program-as-a-local-server"></a>Запуск программы как локального сервера

Если неудобно, выполнение программы в качестве службы, можно временно изменить реестр так, что программа запускается как обычный локального сервера. Просто переименуйте `LocalService` значения в разделе вашей AppID для `_LocalService` и убедитесь, `LocalServer32` раздела вашего CLSID задано правильно. (Обратите внимание, что с помощью DCOMCNFG, чтобы указать, что приложения должны выполняться на другом компьютере переименовывает вашей `LocalServer32` ключа `_LocalServer32`.) Запустить программу, так как локальный сервер занимает несколько секунд при запуске, так как вызов `StartServiceCtrlDispatcher` в `CAtlServiceModuleT::Start` занимает несколько секунд, прежде чем он завершится ошибкой.

## <a name="see-also"></a>См. также

[Советы по отладке](../atl/debugging-tips.md)
