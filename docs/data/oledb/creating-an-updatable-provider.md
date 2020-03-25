---
title: Создание поставщика с возможностью записи
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 2811cd56bdc87282b9d4395a9a79ba9b333dadee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211397"
---
# <a name="creating-an-updatable-provider"></a>Создание поставщика с возможностью записи

Визуальный C++ элемент поддерживает обновляемые поставщики или поставщики, которые могут обновлять (записывать в) хранилище данных. В этом разделе описывается создание обновляемых поставщиков с помощью шаблонов OLE DB.

В этом разделе предполагается, что вы начинаете с помощью работоспособного поставщика. Создание обновляемого поставщика выполняется в два этапа. Сначала необходимо решить, как поставщик будет вносить изменения в хранилище данных. в частности, следует ли выполнять изменения немедленно или отложено, пока не будет выдана команда Update. В разделе «[Создание поставщиков, обновляемых](#vchowmakingprovidersupdatable)» описаны изменения и параметры, которые необходимо выполнить в коде поставщика.

Далее необходимо убедиться, что поставщик содержит все функции для поддержки любых запросов, которые может запросить потребитель. Если потребитель хочет обновить хранилище данных, поставщик должен содержать код, сохраняющий данные в хранилище данных. Например, библиотеку времени выполнения C или MFC можно использовать для выполнения таких операций с источником данных. В разделе «[запись в источник данных](#vchowwritingtothedatasource)» описывается запись в источник данных, работа со значениями NULL и значения по умолчанию, а также установка флагов столбцов.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) — пример обновляемого поставщика. UpdatePV — это то же самое, что и Мипров, но с обновляемой поддержкой.

##  <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a>Создание поставщиков, обновляемых

Ключом к обновлению поставщика является понимание того, какие операции необходимо выполнить поставщику в хранилище данных и как поставщик должен выполнять эти операции. В частности, основная проблема заключается в том, следует ли выполнять обновления хранилища данных немедленно или отложенно (пакетная), пока не будет выдана команда Update.

Сначала необходимо решить, следует ли наследовать от `IRowsetChangeImpl` или `IRowsetUpdateImpl` в классе набора строк. В зависимости от того, какие из этих методов вы выбрали для реализации, будут затронуты следующие функции: `SetData`, `InsertRows`и `DeleteRows`.

- При наследовании от [ировсетчанжеимпл](../../data/oledb/irowsetchangeimpl-class.md)вызов этих трех методов немедленно изменяет хранилище данных.

- При наследовании от [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)методы откладывают изменения в хранилище данных до тех пор, пока не будут вызваны `Update`, `GetOriginalData`или `Undo`. Если обновление включает несколько изменений, они выполняются в пакетном режиме (Обратите внимание, что изменение пакетной обработки может значительно увеличить объем памяти).

Обратите внимание, что `IRowsetUpdateImpl` является производным от `IRowsetChangeImpl`. Таким образом, `IRowsetUpdateImpl` предоставляет возможность изменения и возможности пакетной службы.

### <a name="to-support-updatability-in-your-provider"></a>Поддержка возможности обновления в поставщике

1. В классе набора строк наследуйте от `IRowsetChangeImpl` или `IRowsetUpdateImpl`. Эти классы предоставляют соответствующие интерфейсы для изменения хранилища данных:

   **Добавление IRowsetChange**

   Добавьте `IRowsetChangeImpl` в цепочку наследования, используя следующую форму:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Также добавьте `COM_INTERFACE_ENTRY(IRowsetChange)` в раздел `BEGIN_COM_MAP` класса набора строк.

   **Добавление IRowsetUpdate**

   Добавьте `IRowsetUpdate` в цепочку наследования, используя следующую форму:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > Следует удалить строку `IRowsetChangeImpl` из цепочки наследования. Это единственное исключение в упомянутой выше директиве должно включать код для `IRowsetChangeImpl`.

1. Добавьте следующий объект в карту COM (`BEGIN_COM_MAP ... END_COM_MAP`):

   |  При реализации   |           Добавить к сопоставлению COM             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | При реализации | Добавить в карту набора свойств |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. В команде добавьте следующий элемент в карту набора свойств (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):

   |  При реализации   |                                             Добавить в карту набора свойств                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. В карте набора свойств также следует включить все приведенные ниже параметры, как показано ниже.

    ```cpp
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)

    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)
    ```

   Значения, используемые в этих вызовах макросов, можно найти в ATLDB. h для идентификаторов и значений свойств (если ATLDB. h отличается от документации в Интернете, ATLDB. h заменяет документацию).

   > [!NOTE]
   > Многие параметры `VARIANT_FALSE` и `VARIANT_TRUE` необходимы для шаблонов OLE DB. Спецификация OLE DB сообщает, что они могут быть доступны для чтения и записи, но шаблоны OLE DB могут поддерживать только одно значение.

   **При реализации Ировсетчанжеимпл**

   При реализации `IRowsetChangeImpl`необходимо задать следующие свойства поставщика. Эти свойства в основном используются для запроса интерфейсов через `ICommandProperties::SetProperties`.

   - `DBPROP_IRowsetChange`: параметр автоматически задает `DBPROP_IRowsetChange`.

   - `DBPROP_UPDATABILITY`: битовая маска, указывающая Поддерживаемые методы для `IRowsetChange`: `SetData`, `DeleteRows`или `InsertRow`.

   - `DBPROP_CHANGEINSERTEDROWS`: потребитель может вызвать `IRowsetChange::DeleteRows` или `SetData` для вновь вставленных строк.

   - `DBPROP_IMMOBILEROWS`: набор строк не будет переупорядочивать вставленные или обновленные строки.

   **При реализации IRowsetUpdateImpl**

   При реализации `IRowsetUpdateImpl`необходимо задать следующие свойства поставщика в дополнение к установке всех свойств для `IRowsetChangeImpl`, перечисленных выше:

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: должны быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_OWNUPDATEDELETE`: должны быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_OTHERINSERT`: должны быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_OTHERUPDATEDELETE`: должны быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_REMOVEDELETED`: должны быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > Если вы поддерживаете уведомления, возможно, у вас также есть и другие свойства. см. раздел `IRowsetNotifyCP` для этого списка.

##  <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a>Запись в источник данных

Чтобы выполнить чтение из источника данных, вызовите функцию `Execute`. Для записи в источник данных вызовите функцию `FlushData`. (В общем смысле сброс означает сохранение изменений, внесенных в таблицу или индекс на диск.)

```cpp
FlushData(HROW, HACCESSOR);
```

Аргументы обработчика строк (HROW) и обработчика доступа (HACCESSOR) позволяют указать область для записи. Как правило, в каждый момент времени создается одно поле данных.

Метод `FlushData` записывает данные в формате, в котором они были изначально сохранены. Если вы не переопределяете эту функцию, поставщик будет работать правильно, но изменения не будут сброшены в хранилище данных.

### <a name="when-to-flush"></a>Время записи на диск

Шаблоны поставщика вызывают FlushData каждый раз, когда данные необходимо записать в хранилище данных. обычно (но не всегда) происходит в результате вызова следующих функций:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (при наличии новых данных для вставки в строку)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Как это работает

Потребитель выполняет вызов, который требует сброса (например, Update), и этот вызов передается поставщику, который всегда выполняет следующие действия:

- Вызывает `SetDBStatus` при наличии привязанного значения состояния.

- Проверяет флаги столбцов.

- Вызывает `IsUpdateAllowed`.

Эти три шага помогают обеспечить безопасность. Затем поставщик вызывает `FlushData`.

### <a name="how-to-implement-flushdata"></a>Как реализовать FlushData

Чтобы реализовать `FlushData`, необходимо учитывать несколько проблем:

Убедитесь, что хранилище данных может выполнять обработку изменений.

Обработка значений NULL.

### <a name="handling-default-values"></a>Обработка значений по умолчанию.

Для реализации собственного метода `FlushData` необходимо:

- Перейдите к классу набора строк.

- В классе набора строк добавьте объявление:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Предоставьте реализацию `FlushData`.

Хорошая реализация `FlushData` хранит только обновляемые строки и столбцы. Параметры HROW и HACCESSOR можно использовать для определения текущей строки и столбца, сохраняемых для оптимизации.

Как правило, крупнейший проблемой является работа с собственным собственным хранилищем данных. Если возможно, попробуйте:

- Храните метод записи в хранилище данных как можно более простым.

- Обрабатывайте значения NULL (необязательно, но рекомендуется).

- Обрабатывайте значения по умолчанию (необязательно, но рекомендуется).

Лучше всего иметь в хранилище данных фактически заданные значения NULL и значения по умолчанию. Лучше, если вы можете выполнить экстраполяцию этих данных. В противном случае рекомендуется не допустить значений NULL и по умолчанию.

В следующем примере показано, как `FlushData` реализуется в классе `RUpdateRowset` в примере `UpdatePV` (см. раздел Rowset. h в образце кода):

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)
...
HRESULT FlushData(HROW, HACCESSOR)
{
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");

    USES_CONVERSION;
    enum {
        sizeOfString = 256,
        sizeOfFileName = MAX_PATH
    };
    FILE*    pFile = NULL;
    TCHAR    szString[sizeOfString];
    TCHAR    szFile[sizeOfFileName];
    errcode  err = 0;

    ObjectLock lock(this);

    // From a filename, passed in as a command text,
    // scan the file placing data in the data array.
    if (m_strCommandText == (BSTR)NULL)
    {
        ATLTRACE( "RRowsetUpdate::FlushData -- "
                  "No filename specified\n");
        return E_FAIL;
    }

    // Open the file
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));
    if ((szFile[0] == _T('\0')) ||
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))
    {
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");
        return DB_E_NOTABLE;
    }

    // Iterate through the row data and store it.
    for (long l=0; l<m_rgRowData.GetSize(); l++)
    {
        CAgentMan am = m_rgRowData[l];

        _putw((int)am.dwFixed, pFile);

        if (_tcscmp(&am.szCommand[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);
    }

    if (fflush(pFile) == EOF || fclose(pFile) == EOF)
    {
        ATLTRACE("RRowsetUpdate::FlushData -- "
                 "Couldn't flush or close file\n");
    }

    return S_OK;
}
```

### <a name="handling-changes"></a>Обработка изменений

Чтобы поставщик обрабатывал изменения, сначала необходимо убедиться, что хранилище данных (например, текстовый файл или видеофайл) содержит средства, позволяющие вносить в него изменения. Если это не так, следует создать этот код отдельно от проекта поставщика.

### <a name="handling-null-data"></a>Обработка данных NULL

Возможно, конечный пользователь отправит данные со значением NULL. При записи значений NULL в поля источника данных могут возникать потенциальные проблемы. Представьте приложение, принимающее заказ, которое принимает значения для городов и почтовых индексов. Он может принимать одно или оба значения, но не ни одного, так как в таком случае доставка будет невозможна. Поэтому необходимо ограничить определенные сочетания значений NULL в полях, имеющих смысл для приложения.

Разработчику поставщика необходимо учитывать, как будут храниться эти данные, как будут считываться эти данные из хранилища данных и как указать для пользователя. В частности, необходимо подумать о том, как изменить состояние данных набора строк в источнике данных (например, «Status = NULL»). Вы решаете, какое значение следует возвращать, когда потребитель обращается к полю, содержащему значение NULL.

Взгляните на код в образце UpdatePV; Он показывает, как поставщик может управлять данными NULL. В UpdatePV поставщик хранит данные NULL, записывая строку "NULL" в хранилище данных. Когда он считывает данные NULL из хранилища данных, он видит эту строку, а затем очищает буфер, создавая ПУСТую строку. Он также имеет переопределение `IRowsetImpl::GetDBStatus`, в котором он возвращает DBSTATUS_S_ISNULL если значение данных пустое.

### <a name="marking-nullable-columns"></a>Пометка столбцов, допускающих значение null

Если также реализуются наборы строк схемы (см. `IDBSchemaRowsetImpl`), ваша реализация должна указать в наборе строк DBSCHEMA_COLUMNS (обычно отмеченных в поставщике Ккскскссчемаколсчемаровсет), что столбец допускает значения NULL.

Также необходимо указать, что все столбцы, допускающие значение null, содержат значение DBCOLUMNFLAGS_ISNULLABLE в вашей версии `GetColumnInfo`.

В реализации шаблонов OLE DB, если не удалось пометить столбцы как допускающие значение null, поставщик предполагает, что они должны содержать значение и не позволить потребителю отправить значения NULL.

В следующем примере показано, как функция `CommonGetColInfo` реализована в Купдатекомманд (см. Уппроврс. cpp) в UpdatePV. Обратите внимание, что эти столбцы имеют DBCOLUMNFLAGS_ISNULLABLE для столбцов, допускающих значение null.

```cpp
/////////////////////////////////////////////////////////////////////////////
// CUpdateCommand (in UpProvRS.cpp)

ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)
{
    static ATLCOLUMNINFO _rgColumns[6];
    ULONG ulCols = 0;

    if (bBookmark)
    {
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                            sizeof(DWORD), DBTYPE_BYTES,
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                            DBCOLUMNFLAGS_ISBOOKMARK)
        ulCols++;
    }

    // Next set the other columns up.
    // Add a fixed length entry for OLE DB conformance testing purposes
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,
                        10, 255, GUID_NULL, CAgentMan, dwFixed,
                        DBCOLUMNFLAGS_WRITE |
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    if (pcCols != NULL)
    {
        *pcCols = ulCols;
    }

    return _rgColumns;
}
```

### <a name="default-values"></a>Значения по умолчанию

Как и с ПУСТЫМи данными, вы обязаны изменять значения по умолчанию.

По умолчанию `FlushData` и `Execute` возвращают S_OK. Таким образом, если вы не переопределяете эту функцию, изменения отображаются как успешные (S_OK будут возвращены), но они не будут передаваться в хранилище данных.

В `UpdatePV` примере (в Rowset. h) метод `SetDBStatus` обрабатывает значения по умолчанию следующим образом:

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,
                            ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);

    void* pData = NULL;
    char* pDefaultData = NULL;
    DWORD* pFixedData = NULL;

    switch (*pdbStatus)
    {
        case DBSTATUS_S_DEFAULT:
            pData = (void*)&m_rgRowData[pRow->m_iRowset];
            if (pColInfo->wType == DBTYPE_STR)
            {
                pDefaultData = (char*)pData + pColInfo->cbOffset;
                strcpy_s(pDefaultData, "Default");
            }
            else
            {
                pFixedData = (DWORD*)((BYTE*)pData +
                                          pColInfo->cbOffset);
                *pFixedData = 0;
                return S_OK;
            }
            break;
        case DBSTATUS_S_ISNULL:
        default:
            break;
    }
    return S_OK;
}
```

### <a name="column-flags"></a>Флаги столбцов

Если в столбцах поддерживаются значения по умолчанию, их необходимо задать с помощью метаданных в классе \<поставщика\>класса Счемаровсет. Задайте `m_bColumnHasDefault = VARIANT_TRUE`.

Вы также несете ответственность за установку флагов столбцов, которые указываются с помощью перечислимого типа DBCOLUMNFLAGS. Флаги столбцов описывают характеристики столбцов.

Например, в классе `CUpdateSessionColSchemaRowset` в `UpdatePV` (в Session. h) первый столбец настраивается следующим образом:

```cpp
// Set up column 1
trData[0].m_ulOrdinalPosition = 1;
trData[0].m_bIsNullable = VARIANT_FALSE;
trData[0].m_bColumnHasDefault = VARIANT_TRUE;
trData[0].m_nDataType = DBTYPE_UI4;
trData[0].m_nNumericPrecision = 10;
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));
m_rgRowData.Add(trData[0]);
```

Этот код определяет, помимо прочего, то, что столбец поддерживает значение по умолчанию 0, что оно может быть доступно для записи, и что все данные в столбце имеют одинаковую длину. Если требуется, чтобы данные в столбце имели переменную длину, этот флаг устанавливать не следует.

## <a name="see-also"></a>См. также раздел

[Создание поставщика OLE DB](creating-an-ole-db-provider.md)
