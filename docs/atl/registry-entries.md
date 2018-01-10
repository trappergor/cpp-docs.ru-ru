---
title: "Записи реестра (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: faef0ca0c1c9c4c2986a039b8b1a26517641acd0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="registry-entries"></a>Записи реестра
DCOM представляет концепцию идентификаторов приложения (AppID), какой группы параметров конфигурации для одного или нескольких объектов DCOM в центральном расположении в реестре. Укажите идентификатор AppID, указав его значение в AppID, с именем значения в разделе CLSID объекта.  
  
 По умолчанию служба создается ATL использует идентификатора CLSID как идентификатор GUID для его AppID. В разделе `HKEY_CLASSES_ROOT\AppID`, можно указать параметры, специфичные для DCOM. Изначально существует две записи:  
  
-   `LocalService`, со значением, равным имени службы. Если это значение существует, он используется вместо `LocalServer32` ключа для CLSID.  
  
-   `ServiceParameters`, со значением, равным `-Service`. Это значение указывает параметры, которые будут передаваться службе при ее запуске. Обратите внимание, что эти параметры передаются в службу `ServiceMain` функции, не `WinMain`.  
  
 Также необходимо создать другого ключа в любую службу DCOM `HKEY_CLASSES_ROOT\AppID`. Этот ключ совпадает с именем исполняемого файла и выступает в качестве перекрестных ссылок, как он содержит значение AppID, указывающий AppID записей.  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)

