---
title: Записи реестра (ATL) | Документация Майкрософт
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
ms.openlocfilehash: d74f458e28377dcc0bd7d6800cddc6e227c9f984
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751785"
---
# <a name="registry-entries"></a>Записи реестра

DCOM введена концепция идентификаторов приложений (AppID), какой группы параметров конфигурации для одного или нескольких объектов DCOM в централизованное расположение в реестре. Укажите идентификатор AppID, указав его значение в AppID, с именем значение CLSID объекта.

По умолчанию это служба, созданный ATL использует свой идентификатор как идентификатор GUID для его AppID. В разделе `HKEY_CLASSES_ROOT\AppID`, можно указать записи, относящиеся к DCOM. Изначально существует две записи:

- `LocalService`, со значением, идентичным имени службы. Если это значение существует, он используется вместо `LocalServer32` ключа для CLSID.

- `ServiceParameters`, со значением, равным `-Service`. Это значение указывает параметры, которые будут передаваться в службу, если она запущена. Обратите внимание, что эти параметры передаются в службу `ServiceMain` функция, не `WinMain`.

Также необходимо создать другой ключ в любую службу DCOM `HKEY_CLASSES_ROOT\AppID`. Этот ключ совпадает с именем exe-файла и выступает в качестве перекрестной ссылки, так как он содержит значение AppID, указывающий обратно на записи AppID.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)

