---
title: Запуск программы как локальный сервер | Документы Microsoft
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
ms.openlocfilehash: c2b8a79978528493e02ac5a272dafe8da6fdc1d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360447"
---
# <a name="running-the-program-as-a-local-server"></a>Запуск программы как локальный сервер
Если запустить программу как службу неудобно, можно временно изменить реестр, чтобы программа запускается как обычный локальный сервер. Просто переименуйте `LocalService` значение под вашей AppID для `_LocalService` и убедитесь, `LocalServer32` имеет правильное значение ключа в ваш код CLSID. (Обратите внимание, что с помощью DCOMCNFG для указания запуска приложения на другом компьютере переименовывает вашей `LocalServer32` ключа для `_LocalServer32`.) Запустить программу как локальный сервер принимает несколько секунд во время запуска, так как вызов **StartServiceCtrlDispatcher** в `CAtlServiceModuleT::Start` занимает несколько секунд перед сбоем.  
  
## <a name="see-also"></a>См. также  
 [Советы по отладке](../atl/debugging-tips.md)

