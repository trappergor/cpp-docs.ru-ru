---
title: Записи реестра (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac8e202fc2fc3d58e2d57a9fbfa15264d9fd310e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="registry-entries"></a>Записи реестра
DCOM представляет концепцию идентификаторов приложения (AppID), какой группы параметров конфигурации для одного или нескольких объектов DCOM в центральном расположении в реестре. Укажите идентификатор AppID, указав его значение в AppID, с именем значения в разделе CLSID объекта.  
  
 По умолчанию служба создается ATL использует идентификатора CLSID как идентификатор GUID для его AppID. В разделе `HKEY_CLASSES_ROOT\AppID`, можно указать параметры, специфичные для DCOM. Изначально существует две записи:  
  
-   `LocalService`, со значением, равным имени службы. Если это значение существует, он используется вместо `LocalServer32` ключа для CLSID.  
  
-   `ServiceParameters`, со значением, равным `-Service`. Это значение указывает параметры, которые будут передаваться службе при ее запуске. Обратите внимание, что эти параметры передаются в службу `ServiceMain` функции, не `WinMain`.  
  
 Также необходимо создать другого ключа в любую службу DCOM `HKEY_CLASSES_ROOT\AppID`. Этот ключ совпадает с именем исполняемого файла и выступает в качестве перекрестных ссылок, как он содержит значение AppID, указывающий AppID записей.  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)

