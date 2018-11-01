---
title: Записи реестра (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: b61aae9ba9316dded1dcb11353e52eb2fffd49a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472882"
---
# <a name="registry-entries"></a>Записи реестра

DCOM введена концепция идентификаторов приложений (AppID), какой группы параметров конфигурации для одного или нескольких объектов DCOM в централизованное расположение в реестре. Укажите идентификатор AppID, указав его значение в AppID, с именем значение CLSID объекта.

По умолчанию это служба, созданный ATL использует свой идентификатор как идентификатор GUID для его AppID. В разделе `HKEY_CLASSES_ROOT\AppID`, можно указать записи, относящиеся к DCOM. Изначально существует две записи:

- `LocalService`, со значением, идентичным имени службы. Если это значение существует, он используется вместо `LocalServer32` ключа для CLSID.

- `ServiceParameters`, со значением, равным `-Service`. Это значение указывает параметры, которые будут передаваться в службу, если она запущена. Обратите внимание, что эти параметры передаются в службу `ServiceMain` функция, не `WinMain`.

Также необходимо создать другой ключ в любую службу DCOM `HKEY_CLASSES_ROOT\AppID`. Этот ключ совпадает с именем exe-файла и выступает в качестве перекрестной ссылки, так как он содержит значение AppID, указывающий обратно на записи AppID.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)

