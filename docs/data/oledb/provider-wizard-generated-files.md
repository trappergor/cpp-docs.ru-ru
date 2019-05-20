---
title: Созданные мастером поставщика файлы
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: de5c9056402cb1db25240772eb3c592523daafae
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525320"
---
# <a name="provider-wizard-generated-files"></a>Созданные мастером поставщика файлы

::: moniker range="vs-2019"

Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="vs-2017"

**Мастер поставщика OLE DB в ATL** создает следующие файлы. В указанных ниже разделах используется короткое имя *Custom*, но точные имена файлов зависят от выбора при создании поставщика.

|Имя файла|Описание|
|---------------|-----------------|
|*Custom*RS.cpp|Содержит вспомогательный метод `Execute` команды и схему столбцов поставщика.|
|*Custom*DS.h|Реализует объект источника данных. Этот файл заголовка содержит схему свойств для свойств источника данных.|
|*Custom*RS.h|Реализует объекты команды и набора строк. Этот файл заголовка содержит схему свойств для набора строк и свойств команды.|
|*Custom*Sess.h|Реализует объект сеанса. Этот файл заголовка содержит схему свойств для свойств сеанса.|
|*Custom*.rgs|Содержит зарегистрированные объекты, создаваемые **мастером поставщика OLE DB**.|

::: moniker-end

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
