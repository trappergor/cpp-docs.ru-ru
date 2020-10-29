---
title: Созданные мастером поставщика файлы
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 3bc680e5999c077dda384823ec4f67d2456af284
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924330"
---
# <a name="provider-wizard-generated-files"></a>Созданные мастером поставщика файлы

::: moniker range="msvc-160"

Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=msvc-150"

**Мастер поставщика OLE DB в ATL** создает следующие файлы. В указанных ниже разделах используется короткое имя *Custom* , но точные имена файлов зависят от выбора при создании поставщика.

|Имя файла|Описание|
|---------------|-----------------|
|*Custom* RS.cpp|Содержит вспомогательный метод `Execute` команды и схему столбцов поставщика.|
|*Custom* DS.h|Реализует объект источника данных. Этот файл заголовка содержит схему свойств для свойств источника данных.|
|*Custom* RS.h|Реализует объекты команды и набора строк. Этот файл заголовка содержит схему свойств для набора строк и свойств команды.|
|*Custom* Sess.h|Реализует объект сеанса. Этот файл заголовка содержит схему свойств для свойств сеанса.|
|*Custom* .rgs|Содержит зарегистрированные объекты, создаваемые **мастером поставщика OLE DB** .|

::: moniker-end

## <a name="see-also"></a>См. также статью

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
