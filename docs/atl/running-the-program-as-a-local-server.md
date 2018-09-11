---
title: Запуск программы как локального сервера | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7ff7c2f7564a5da2c7a1db3913526a95660fe1d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754687"
---
# <a name="running-the-program-as-a-local-server"></a>Запуск программы как локального сервера

Если неудобно, выполнение программы в качестве службы, можно временно изменить реестр так, что программа запускается как обычный локального сервера. Просто переименуйте `LocalService` значения в разделе вашей AppID для `_LocalService` и убедитесь, `LocalServer32` раздела вашего CLSID задано правильно. (Обратите внимание, что с помощью DCOMCNFG, чтобы указать, что приложения должны выполняться на другом компьютере переименовывает вашей `LocalServer32` ключа `_LocalServer32`.) Запустить программу, так как локальный сервер занимает несколько секунд при запуске, так как вызов `StartServiceCtrlDispatcher` в `CAtlServiceModuleT::Start` занимает несколько секунд, прежде чем он завершится ошибкой.

## <a name="see-also"></a>См. также

[Советы по отладке](../atl/debugging-tips.md)

