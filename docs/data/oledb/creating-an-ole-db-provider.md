---
title: Создание поставщика OLE DB
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
ms.openlocfilehash: 3e46e87b0d5d538a0f9fd7e231debfef3fa95210
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036118"
---
# <a name="creating-an-ole-db-provider"></a>Создание поставщика OLE DB

Рекомендуемый способ создания поставщика OLE DB является использование мастера для создания проекта ATL COM и поставщика, а затем измените файлы с помощью шаблонов OLE DB. При настройке вашего поставщика, можно закомментировать нежелательные свойства и добавить дополнительные интерфейсы.

Порядок действий таков:

1. Используйте **мастер проектов ATL** для создания файлов базовый проект и **мастер поставщика ATL OLEDB** для создания поставщика (выберите **поставщик OLEDB библиотеки ATL** из **Установленные** > **Visual C++** > **ATL** папку в **Добавление нового элемента**).

   > [!NOTE]
   > Проект должен включать поддержку MFC, прежде чем добавлять **поставщик OLEDB библиотеки ATL**.

1. Измените код в `Execute` метод в [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md). Например, см. в разделе [чтение строк в поставщик OLE DB](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

1. Изменить свойства карты в [CustomDS.h](cmyprovidersource-myproviderds-h.md), [CustomSess.h](cmyprovidersession-myprovidersess-h.md), и [CustomRS.h](cmyproviderrowset-myproviderrs-h.md). Мастер создает сопоставления свойств, которые содержат все свойства, которые может реализовать поставщик. Просмотрите сопоставления свойств и удалите или закомментируйте свойства, которые поставщик должен поддерживать.

1. Обновить PROVIDER_COLUMN_MAP, которую можно найти в [CCustomRowset(CustomRS.h)](cmyproviderrowset-myproviderrs-h.md). Например, см. в разделе [хранения строк в поставщик OLE DB](../../data/oledb/storing-strings-in-the-ole-db-provider.md).

1. Когда будете готовы для проверки поставщика, можно проверить его, необходимо найти поставщик в перечислении поставщиков. Примеры кода теста, который находит поставщика в перечислении, см. в разделе ["CatDB"](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) и [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) образцы или только в примере в [реализация простых объектов получателей](../../data/oledb/implementing-a-simple-consumer.md).

1. Добавьте любые дополнительные интерфейсы, которые вам нужны. Например, см. в разделе [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md).

   > [!NOTE]
   > По умолчанию мастера создают код, который OLE DB уровня 0 соответствует. Чтобы убедиться, что приложение остается совместимым с уровнем 0, не удаляйте любой из этих интерфейсов, созданный мастером из кода.

## <a name="see-also"></a>См. также

[Пример "CatDB". Обозреватель схемы источника данных](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[Образец DBViewer: Обозреватель базы данных](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
