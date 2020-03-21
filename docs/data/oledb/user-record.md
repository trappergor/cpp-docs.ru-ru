---
title: Запись пользователя
ms.date: 05/09/2019
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
ms.openlocfilehash: 4a8fb6c9eeee3736501a04a095bdd763de16de7d
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079005"
---
# <a name="user-record"></a>Запись пользователя

> [!NOTE]
> Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.

Запись пользователя предоставляет структуру кода и данных, представляющую собой данные столбца для набора строк. Запись пользователя может создаваться во время компиляции или выполнения. При создании поставщика с помощью службы **Мастер поставщика ATL OLE DB** мастер создает запись пользователя по умолчанию, которая выглядит следующим образом (при условии, что указано имя поставщика [короткое имя] из *MyProvider*).

```cpp
class CWindowsFile:
   public WIN32_FIND_DATA
{
public:
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
  
};
```

При взаимодействии с клиентом шаблоны поставщика OLE DB обрабатывают все особенности OLE DB. Чтобы получить данные столбца, необходимые для ответа, поставщик вызывает функцию `GetColumnInfo`, которую необходимо поместить в запись пользователя. Вы можете использовать явное переопределение `GetColumnInfo` в пользовательской записи, например, объявив ее в H-файл, как описано в этом примере.

```cpp
template <class T>
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)
```

Это соответствует следующему.

```cpp
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)
```

Затем запустите `GetColumnInfo` в CPP-файле записи пользователя.

Макросы PROVIDER_COLUMN_MAP упрощают создание функции `GetColumnInfo`.

- BEGIN_PROVIDER_COLUMN_MAP определяет прототип функции и статический массив структур `ATLCOLUMNINFO`.

- PROVIDER_COLUMN_ENTRY определяет и инициализирует отдельную `ATLCOLUMNINFO`.

- END_PROVIDER_COLUMN_MAP закрывает массив и функцию. Он также перемещает число элементов массива в параметр *pcCols*.

При создании записи пользователя во время выполнения `GetColumnInfo` использует параметр *pThis* для получения указателя на экземпляр набора строк или команды. Команды и наборы строк должны поддерживать интерфейс `IColumnsInfo`, поэтому из этого указателя может быть взята информация о столбце.

Команда `CommandClass` и набор строк `RowsetClass` используют эту запись пользователя.

Более подробный пример переопределения `GetColumnInfo` в записи пользователя см. в статье [Dynamically Determining Columns Returned to the Consumer](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md) (Динамично определяемые столбцы, возвращенные объекту-получателю).

## <a name="see-also"></a>См. также:

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
