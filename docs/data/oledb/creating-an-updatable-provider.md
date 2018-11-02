---
title: Создание поставщика с возможностью записи
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 39e0fffa10af560537a932d503946ec2469bef5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570590"
---
# <a name="creating-an-updatable-provider"></a>Создание поставщика с возможностью записи

Visual C++ поддерживает поставщики, которые могут обновлять (запись) в хранилище данных. В этом разделе описывается создание обновляемых поставщиков, с помощью шаблонов OLE DB.

В этом разделе предполагается, что вы начинаете с рабочий поставщик. Существуют два шага для создания поставщика с возможностью записи. Во-первых, необходимо решить, как поставщик будет внести изменения в хранилище данных; в частности ли изменения должны выполняться немедленно, или отложить, пока не будет выполнена команда обновления. Раздел "[внесения поставщиков с возможностью записи](#vchowmakingprovidersupdatable)" описаны изменения и параметры, необходимо выполнить в код поставщика.

Затем необходимо убедиться в том, что поставщик обладает всеми функциями для поддержки любых потребитель может запросить его. Если необходимо обновить хранилище данных, поставщик должен содержать код, который сохраняет данные в хранилище данных. Например можно использовать библиотеки времени выполнения C или MFC для выполнения таких операций в источнике данных. Раздел "[записи в источник данных](#vchowwritingtothedatasource)» описывается, как запись в источник данных, обрабатывать значения NULL и значение по умолчанию и установить флаги столбца.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) является примером поставщика с возможностью записи. UpdatePV одинаков как поставщика MyProv, но записи.

##  <a name="vchowmakingprovidersupdatable"></a> Создание обновляемых поставщиков

Ключевую поставщик обновляемых является понимание того, какие операции должен выполнять в хранилище данных, а также способ поставщика для выполнения этих операций. В частности, основной вопрос заключается в хранилище данных, установки обновлений для незамедлительно или отложена (пакетная) пока не будет выполнена команда обновления.

Необходимо решить, нужно ли наследовать от `IRowsetChangeImpl` или `IRowsetUpdateImpl` класса набора строк. В зависимости от того, какой из этих вы решили реализовать, будут применяться функциональные возможности из трех методов: `SetData`, `InsertRows`, и `DeleteRows`.

- При наследовании от [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), вызов этих трех методов немедленно изменяет хранилище данных.

- При наследовании от [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), методы откладывания изменений в хранилище данных, пока не будет вызван `Update`, `GetOriginalData`, или `Undo`. Если обновление включает в себя несколько изменений, они выполняются в пакетном режиме (Обратите внимание, что Пакетная обработка изменений можно добавить издержки значительный объем памяти).

Обратите внимание, что `IRowsetUpdateImpl` является производным от `IRowsetChangeImpl`. Таким образом `IRowsetUpdateImpl` позволяет изменять возможностей, а также в пакетном режиме.

### <a name="to-support-updatability-in-your-provider"></a>Для поддержки возможности обновления в поставщике

1. В классе набора строк наследуют `IRowsetChangeImpl` или `IRowsetUpdateImpl`. Эти классы обеспечивают необходимые интерфейсы для изменения хранилища данных:

     **Добавление IRowsetChange**

   Добавить `IRowsetChangeImpl` в цепочку наследования с помощью этой формы:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Кроме того, добавить `COM_INTERFACE_ENTRY(IRowsetChange)` для `BEGIN_COM_MAP` разделе класса набора строк.

     **Добавление IRowsetUpdate**

   Добавить `IRowsetUpdate` в цепочку наследования с помощью этой формы:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

    > [!NOTE]
    > Следует удалить `IRowsetChangeImpl` строки из цепочки наследования. Это исключение для упомянутой выше директивы должно содержать код для `IRowsetChangeImpl`.

1. Добавьте следующее сопоставление COM (`BEGIN_COM_MAP ... END_COM_MAP`):

    |Если вы реализуете|Добавление сопоставления COM|
    |----------------------|--------------------|
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|

1. В команде, добавьте следующий сопоставление набора свойств (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):

    |Если вы реализуете|Добавить сопоставление набора свойств|
    |----------------------|-----------------------------|
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|

1. В сопоставление набора свойств вам также необходимо включить все необходимые параметры, как они указаны ниже:

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

   Можно найти значения, используемые в этих вызовов макросов путем поиска в Atldb.h идентификаторы свойств и значений (если Atldb.h отличается от электронной документации, Atldb.h замещает ее).

    > [!NOTE]
    > Многие из `VARIANT_FALSE` и `VARIANT_TRUE` необходимые параметры в шаблонах OLE DB; в спецификации OLE DB говорится, они могут быть чтения и записи, но шаблоны OLE DB поддерживает только одно значение.

     **Если вы реализуете IRowsetChangeImpl**

   Если вы реализуете `IRowsetChangeImpl`, необходимо задать следующие свойства для поставщика. Эти свойства в основном используются для запроса интерфейсов с помощью `ICommandProperties::SetProperties`.

    - `DBPROP_IRowsetChange`: Задание при этом автоматически наборы `DBPROP_IRowsetChange`.

    - `DBPROP_UPDATABILITY`: Битовая маска, указывающая поддерживаемые методы на `IRowsetChange`: `SetData`, `DeleteRows`, или `InsertRow`.

    - `DBPROP_CHANGEINSERTEDROWS`: Пользователь может вызвать `IRowsetChange::DeleteRows` или `SetData` для вставленных строк.

    - `DBPROP_IMMOBILEROWS`: Набор строк не будет переупорядочивать вставленные или обновленные строки.

     **Если вы реализуете IRowsetUpdateImpl**

   Если вы реализуете `IRowsetUpdateImpl`, необходимо задать следующие свойства для поставщика, в дополнение к заданию свойств для `IRowsetChangeImpl` перечисленных выше:

    - `DBPROP_IRowsetUpdate`.

    - `DBPROP_OWNINSERT`: Должен иметь значение VARIANT_TRUE и READ_ONLY.

    - `DBPROP_OWNUPDATEDELETE`: Должен иметь значение VARIANT_TRUE и READ_ONLY.

    - `DBPROP_OTHERINSERT`: Должен иметь значение VARIANT_TRUE и READ_ONLY.

    - `DBPROP_OTHERUPDATEDELETE`: Должен иметь значение VARIANT_TRUE и READ_ONLY.

    - `DBPROP_REMOVEDELETED`: Должен иметь значение VARIANT_TRUE и READ_ONLY.

    - `DBPROP_MAXPENDINGROWS`.

        > [!NOTE]
        > Если требуется поддержка уведомлений, также возможно, некоторые другие свойства; см. в разделе `IRowsetNotifyCP` для этого списка.

##  <a name="vchowwritingtothedatasource"></a> Запись в источник данных

Для считывания из источника данных, вызвать `Execute` функции. Чтобы записать в источник данных, вызовите `FlushData` функции. (В общем смысле, очистите означает сохранение изменений, внесенные в таблицы или индекса на диск).

```cpp
FlushData(HROW, HACCESSOR);
```

Маркер строки (HROW) и аргументы (HACCESSOR) дескриптор метода доступа позволяют пользователю указать область записи. Как правило одновременно записывают одного поля данных.

`FlushData` Метод записывает данные в формате, в котором он изначально был сохранен. Если эта функция не переопределяется, поставщик будет работать правильно, но изменения не будут сброшены в хранилище данных.

### <a name="when-to-flush"></a>Когда на диск

Шаблоны поставщика вызовите FlushData всякий раз, когда данные должны записываться в хранилище данных; Это обычно (но не всегда) происходит в результате вызовов следующих функций:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (если есть новые данные для вставки в строке)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Принцип работы

Потребитель вызывает метод, требующий обновления данных (например, обновление), и этот вызов передается поставщику, который всегда делает следующее:

- Вызовы `SetDBStatus` каждый раз, когда у вас есть значение состояния привязан.

- Проверяет флаги столбца.

- Вызывает `IsUpdateAllowed`.

Эти три шага помогают обеспечить безопасность. Затем поставщик вызывает `FlushData`.

### <a name="how-to-implement-flushdata"></a>Как реализовать FlushData

Для реализации `FlushData`, необходимо учитывать несколько вопросов:

Убедившись, что хранилище данных может обрабатывать изменения.

Обработка значений NULL.

### <a name="handling-default-values"></a>Обработка значений по умолчанию.

Чтобы реализовать свою собственную `FlushData` методе, вам потребуется:

- Перейти к классу набора строк.

- В наборе строк поместить класс следующее объявление:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Предоставляет реализацию `FlushData`.

Рекомендуется `FlushData` сохраняет только те строки и столбцы, которые необходимо обновить. Параметры HROW и HACCESSOR можно использовать для определения текущей строки и столбца, сохраняемые для оптимизации.

Как правило самая сложная задача — работа с собственное хранилище данных в собственном формате. Если это возможно попробуйте:

- Сохраните выбранный метод записи в хранилище данных, как можно более простым.

- Обработка значений NULL (необязательно, но желательно).

- Обработка значений по умолчанию (необязательно, но желательно).

Лучший способ — хранить фактические значения в хранилище данных для значений NULL и значение по умолчанию. Проще всего, если можно экстраполировать эти данные. В противном случае рекомендуется не допускает значений NULL и значение по умолчанию.

В следующем примере показан как `FlushData` реализуется в `RUpdateRowset` в класс `UpdatePV` пример (см. в разделе Rowset.h в образце кода):

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

Для поставщика для обработки изменений необходимо сначала убедитесь, что хранилище данных (например, текстовый файл или видеофайл) содержит средства, которые позволяют вносить изменения на нем. Если этого не произошло, этот код следует создать отдельно от проекта поставщика.

### <a name="handling-null-data"></a>Обработка значений NULL

Вполне возможно, что конечный пользователь отправит данные значение NULL. При записи значений NULL для поля в источнике данных, может быть потенциальных проблем. Представим себе приложение заказы, который принимает значения для Город и почтовый индекс. приложение может принять один или оба значения, но не ни одного, так как в этом случае может быть организовано доставки. Поэтому необходимо ограничить определенные комбинации значений NULL в полях, которые лучше подходят для вашего приложения.

Разработчик поставщика которые следует учесть, вы будете хранить эти данные, как будет считывать данные из хранилища данных и как можно указать, что для пользователя. В частности, необходимо учитывать способ изменения состояния данных набора строк в источнике данных (например, DataStatus = NULL). Вы решите, какое значение возвращается, когда объект-получатель обращается к полю, содержащему значение NULL.

Взгляните на код в образце UpdatePV; Здесь показано, как поставщик может обрабатывать данные значение NULL. В этом примере поставщик хранит данные значение NULL, записывая строку «NULL» в хранилище данных. При считывании NULL из хранилища данных, он видит эту строку и очищает буфер, создание строки NULL. Она также содержит переопределение `IRowsetImpl::GetDBStatus` в котором она возвращает значение DBSTATUS_S_ISNULL, если это значение данных пуста.

### <a name="marking-nullable-columns"></a>Пометка столбцов со значением NULL

При реализации наборы строк схемы (см. в разделе `IDBSchemaRowsetImpl`), в реализации необходимо указать в наборе строк DBSCHEMA_COLUMNS (обычно знаменуется в поставщике CxxxSchemaColSchemaRowset), является ли столбец допускает значения NULL.

Необходимо также указать, что все столбцы, допускающие значение NULL будет содержать значение DBCOLUMNFLAGS_ISNULLABLE в вашей версии `GetColumnInfo`.

В реализации шаблонов OLE DB Если не удается выделить столбцы, допускающие значение NULL, поставщик предполагает, что они должны содержать значения и не позволит потребителю отправлять значения null.

В следующем примере показан способ `CommonGetColInfo` функция реализуется значений свойствам (см. в разделе UpProvRS.cpp) в этом примере. Обратите внимание на то, как столбцы имеют этот DBCOLUMNFLAGS_ISNULLABLE для столбцов со значением NULL.

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

Как со значением NULL, также необходимо обрабатывать изменения значения по умолчанию.

Значение по умолчанию `FlushData` и `Execute` возвращает значение S_OK. Таким образом, если эта функция не переопределяется, изменения отображаются для успешного выполнения (будет возвращено значение S_OK), но они не передаются в хранилище данных.

В `UpdatePV` (в файле Rowset.h) `SetDBStatus` метод обрабатывает значения по умолчанию следующим образом:

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

Если поддержка значений по умолчанию для столбцов, необходимо задать ее, используя метаданные \<класс поставщика\>SchemaRowset класса. Задайте `m_bColumnHasDefault = VARIANT_TRUE`.

Имеется также необходимо установить флаги столбцов, которые указываются с помощью DBCOLUMNFLAGS перечисляемого типа. Флаги столбцов описывают характеристики столбца.

Например, в `CUpdateSessionColSchemaRowset` в класс `UpdatePV` (в Session.h), первый столбец настраивается таким образом:

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

Этот код указывает, помимо прочего, что столбец поддерживает значение по умолчанию 0, что доступен для записи, и что все данные в столбце имеют одинаковую длину. Если требуется, чтобы данные в столбце должны быть переменной длины, не устанавливает этот флаг.

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](creating-an-ole-db-provider.md)