---
title: "Запуск программы как локальный сервер | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e398bfed0174e4ec2a262ea03076ed17881f900
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="running-the-program-as-a-local-server"></a>Запуск программы как локальный сервер
Если запустить программу как службу неудобно, можно временно изменить реестр, чтобы программа запускается как обычный локальный сервер. Просто переименуйте `LocalService` значение под вашей AppID для `_LocalService` и убедитесь, `LocalServer32` имеет правильное значение ключа в ваш код CLSID. (Обратите внимание, что с помощью DCOMCNFG для указания запуска приложения на другом компьютере переименовывает вашей `LocalServer32` ключа для `_LocalServer32`.) Запустить программу как локальный сервер принимает несколько секунд во время запуска, так как вызов **StartServiceCtrlDispatcher** в `CAtlServiceModuleT::Start` занимает несколько секунд перед сбоем.  
  
## <a name="see-also"></a>См. также  
 [Советы по отладке](../atl/debugging-tips.md)

