---
title: Запуск программы как локального сервера
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: 9a55dba861457eae888f519fb3bbd6c7a66e623c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610864"
---
# <a name="running-the-program-as-a-local-server"></a>Запуск программы как локального сервера

Если неудобно, выполнение программы в качестве службы, можно временно изменить реестр так, что программа запускается как обычный локального сервера. Просто переименуйте `LocalService` значения в разделе вашей AppID для `_LocalService` и убедитесь, `LocalServer32` раздела вашего CLSID задано правильно. (Обратите внимание, что с помощью DCOMCNFG, чтобы указать, что приложения должны выполняться на другом компьютере переименовывает вашей `LocalServer32` ключа `_LocalServer32`.) Запустить программу, так как локальный сервер занимает несколько секунд при запуске, так как вызов `StartServiceCtrlDispatcher` в `CAtlServiceModuleT::Start` занимает несколько секунд, прежде чем он завершится ошибкой.

## <a name="see-also"></a>См. также

[Советы по отладке](../atl/debugging-tips.md)

