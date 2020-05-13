---
title: Создание поставщика с возможностью записи
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 720ceba397d17642402de4d44cbb4481852fa153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365557"
---
# <a name="creating-an-updatable-provider"></a>Создание поставщика с возможностью записи

Визуальный КЗ поддерживает updatable провайдеров или поставщиков, которые могут обновить (запись) хранилище данных. На этой теме обсуждается вопрос о том, как создавать updatable провайдеров с помощью шаблонов OLE DB.

Эта тема предполагает, что вы начинаете с работоспособного поставщика. Существует два шага к созданию поставщика updatable. Сначала необходимо решить, как поставщик внесет изменения в хранилище данных; в частности, должны ли изменения быть сделаны немедленно или отложено до тех пор, пока не будет выпущена команда обновления. Раздел[«Создание провайдеров Updatable»](#vchowmakingprovidersupdatable)описывает изменения и настройки, которые необходимо сделать в коде поставщика.

Далее необходимо убедиться, что поставщик содержит все функциональные возможности для поддержки всего, что может запрашивать потребитель. Если потребитель хочет обновить хранилище данных, поставщик должен содержать код, который сохраняет данные в хранилище данных. Например, для выполнения таких операций в источнике данных можно использовать библиотеку C Run-Time или MFC. В разделе[«Письмо источнику данных»](#vchowwritingtothedatasource)описывается, как писать в источник данных, иметь дело с значениями NULL и по умолчанию, а также устанавливать флаги столбцов.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) является примером updatable поставщика. UpdatePV такой же, как MyProv, но с updatable поддержки.

## <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a>Создание провайдеров Updatable

Ключом к тому, чтобы сделать провайдера updatable, является понимание того, какие операции вы хотите, чтобы ваш провайдер выполнял в хранилище данных и как вы хотите, чтобы провайдер выполнял эти операции. В частности, основная проблема заключается в том, следует ли немедленно проводить обновления в хранилище данных или откладывать (пакетировать) до тех пор, пока не будет выпущена команда обновления.

Сначала необходимо решить, следует `IRowsetChangeImpl` `IRowsetUpdateImpl` ли наследовать от класса rowset или в вашем классе. В зависимости от того, какой из них вы решите `SetData`реализовать, функциональность трех методов будет затронута: , `InsertRows`и `DeleteRows`.

- Если вы наследуете от [IRowsetChangeImpl,](../../data/oledb/irowsetchangeimpl-class.md)вызов этих трех методов немедленно изменяет хранилище данных.

- Если вы наследуете от [IRowsetUpdateImpl,](../../data/oledb/irowsetupdateimpl-class.md)методы откладывают `Update`изменения `GetOriginalData`в `Undo`хранилище данных до тех пор, пока вы не позвоните, или . Если обновление включает в себя несколько изменений, они выполняются в пакетном режиме (обратите внимание, что изменения пакетирования могут добавить значительные накладные расходы памяти).

Обратите `IRowsetUpdateImpl` внимание, `IRowsetChangeImpl`что происходит от . Таким `IRowsetUpdateImpl` образом, дает вам возможность изменения плюс возможность пакетной.

### <a name="to-support-updatability-in-your-provider"></a>Поддержка updatability в вашем провайдере

1. В вашем классе rowset, наследовать от `IRowsetChangeImpl` или `IRowsetUpdateImpl`. Эти классы предоставляют соответствующие интерфейсы для изменения хранилища данных:

   **Добавление IRowsetChange**

   Добавьте `IRowsetChangeImpl` к цепочке наследования, используя эту форму:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Также `COM_INTERFACE_ENTRY(IRowsetChange)` добавьте `BEGIN_COM_MAP` в раздел в классе rowset.

   **Добавление IRowsetUpdate**

   Добавьте `IRowsetUpdate` к цепочке наследования, используя эту форму:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > Вы должны `IRowsetChangeImpl` удалить строку из цепочки наследования. Это одно исключение из упомянутой ранее `IRowsetChangeImpl`директивы должно включать код для .

1. Добавьте следующее к`BEGIN_COM_MAP ... END_COM_MAP`карте COM ():

   |  При реализации   |           Добавление к карте COM             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | При реализации | Добавление к карте набора свойств |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. В вашей команде добавьте следующее`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`в карту набора свойств ( ):

   |  При реализации   |                                             Добавление к карте набора свойств                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. На карте набора свойств вы также должны включить все следующие параметры по мере их появления ниже:

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

   Вы можете найти значения, используемые в этих макро-звонков, глядя в Atldb.h для идентификаторов свойств и значений (если Atldb.h отличается от онлайн-документации, Atldb.h заменяет документацию).

   > [!NOTE]
   > Многие `VARIANT_FALSE` настройки `VARIANT_TRUE` и настройки требуются шаблонами OLE DB; спецификация OLE DB говорит, что их можно читать/писать, но шаблоны OLE DB могут поддерживать только одно значение.

   **При реализации IRowsetChangeImpl**

   При реализации `IRowsetChangeImpl`необходимо установить следующие свойства на своем поставщике. Эти свойства в основном используются `ICommandProperties::SetProperties`для запроса интерфейсов через .

   - `DBPROP_IRowsetChange`: Установка этого `DBPROP_IRowsetChange`автоматически устанавливает .

   - `DBPROP_UPDATABILITY`: битовая маска с указанием `DeleteRows`поддерживаемых `InsertRow`методов на `IRowsetChange`: `SetData`, или .

   - `DBPROP_CHANGEINSERTEDROWS`: Потребитель `IRowsetChange::DeleteRows` `SetData` может позвонить или для вновь вставленных строк.

   - `DBPROP_IMMOBILEROWS`: Rowset не будет переупорядочить вставленные или обновленные строки.

   **При реализации IRowsetUpdateImpl**

   При реализации `IRowsetUpdateImpl`необходимо установить следующие свойства на своем поставщике, `IRowsetChangeImpl` в дополнение к установке всех свойств для ранее перечисленных:

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: Должно быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_OWNUPDATEDELETE`: Должно быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_OTHERINSERT`: Должно быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_OTHERUPDATEDELETE`: Должно быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_REMOVEDELETED`: Должно быть READ_ONLY и VARIANT_TRUE.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > Если вы поддерживаете уведомления, у вас также могут быть и другие свойства; смотрите раздел `IRowsetNotifyCP` для этого списка.

## <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a>Запись в источник данных

Чтобы прочитать из источника `Execute` данных, позвоните в функцию. Чтобы написать в источник `FlushData` данных, позвоните в функцию. (В общем смысле, флеш означает сохранить изменения, которые вы внесли в таблицу или индекс на диск.)

```cpp
FlushData(HROW, HACCESSOR);
```

Аргументы в области стержа( HROW) и ручки аксессуаров (HACCESSOR) позволяют указать область для записи. Как правило, вы пишете одно поле данных одновременно.

Метод `FlushData` записывает данные в формате, в котором они первоначально хранились. Если вы не отмените эту функцию, ваш провайдер будет функционировать правильно, но изменения не будут смыты в хранилище данных.

### <a name="when-to-flush"></a>Когда флеш

Шаблоны поставщика вызывают FlushData всякий раз, когда данные должны быть записаны в хранилище данных; это обычно (но не всегда) происходит в результате вызовов на следующие функции:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows`(если есть новые данные для вставки в строку)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Как это работает

Потребитель делает вызов, который требует флеша (например, обновление), и этот звонок передается поставщику, который всегда делает следующее:

- Вызывает `SetDBStatus` всякий раз, когда у вас есть статус значение связано.

- Проверка флагов столбцов.

- Вызывает `IsUpdateAllowed`.

Эти три шага помогают обеспечить безопасность. Затем провайдер `FlushData`звонит .

### <a name="how-to-implement-flushdata"></a>Как реализовать FlushData

Для `FlushData`реализации необходимо учитывать несколько вопросов:

Обеспечение того, чтобы хранилище данных мог обрабатывать изменения.

Обработка значений NULL.

### <a name="handling-default-values"></a>Обработка значений по умолчанию.

Для реализации `FlushData` собственного метода необходимо:

- Перейти к вашему классу rowset.

- В классе rowset положить декларацию:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Обеспечить реализацию `FlushData`.

Хорошая реализация `FlushData` магазинов только строки и столбцы, которые на самом деле обновляются. Параметры HROW и HACCESSOR можно использовать для определения текущей строки и столбца, хранящихся для оптимизации.

Как правило, самой большой проблемой является работа с собственным родным хранилищем данных. Если возможно, попробуйте:

- Храните метод записи в хранилище данных как можно проще.

- Обработка значения NULL (необязательно, но рекомендуется).

- Обработка значений по умолчанию (необязательно, но рекомендуется).

Лучше всего иметь фактические определенные значения в хранилище данных для значения NULL и по умолчанию. Лучше всего, если вы можете экстраполировать эти данные. В противом случае рекомендуется не допускать значения NULL и по умолчанию.

Следующий пример `FlushData` показывает, как `RUpdateRowset` реализуется `UpdatePV` в классе в выборке (см. Rowset.h в коде образца):

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

Для того чтобы ваш провайдер мог обрабатывать изменения, сначала необходимо убедиться, что в хранилище данных (например, текстовый файл или видеофайл) есть средства, позволяющие вносить изменения в него. Если это не так, необходимо создать этот код отдельно от проекта поставщика.

### <a name="handling-null-data"></a>Обработка данных NULL

Не исключено, что конечный пользователь отправит данные NULL. При написании значений NULL в поля в источнике данных могут возникнуть потенциальные проблемы. Представьте себе приложение, принимающее заказы, которое принимает значения для городского и почтового индекса; она может принять любое или оба значения, но не и то, ни другое, поскольку в этом случае доставка будет невозможна. Поэтому необходимо ограничить определенные комбинации значений NULL в полях, которые имеют смысл для вашего приложения.

Как разработчик-поставщик, вы должны рассмотреть, как вы будете хранить эти данные, как вы будете читать эти данные из хранилища данных, и как вы указать, что для пользователя. В частности, необходимо рассмотреть вопрос об изменении состояния данных данных строк в источнике данных (например, DataStatus и NULL). Вы сами решаете, какое значение следует возвращать, когда потребитель получает доступ к поле, содержащему значение NULL.

Посмотрите на код в образце UpdatePV; он иллюстрирует, как поставщик может обрабатывать данные NULL. В UpdatePV поставщик хранит данные NULL, написав строку "NULL" в хранилище данных. Когда он считывает данные NULL из хранилища данных, он видит эту строку, а затем опустошает буфер, создавая строку NULL. Он также имеет переопределение, `IRowsetImpl::GetDBStatus` в котором он возвращает DBSTATUS_S_ISNULL, если это значение данных пусто.

### <a name="marking-nullable-columns"></a>Маркировка недействительных колонн

Если вы также реализуете строки `IDBSchemaRowsetImpl`схем (см.), ваша реализация должна указать в DBSCHEMA_COLUMNS строке (обычно отмеченной в вашем поставщике CxxxSchemaColChemaRowset), что столбец является недействительным.

Также необходимо указать, что все недействительные столбцы содержат `GetColumnInfo`DBCOLUMNFLAGS_ISNULLABLE значение в вашей версии.

В реализации шаблонов OLE DB, если вы не помечаете столбцы как недействительные, поставщик предполагает, что они должны содержать значение и не позволит потребителю отправить его нулевые значения.

Следующий пример показывает, как `CommonGetColInfo` функция реализована в CUpdateCommand (см. UpProvRS.cpp) в UpdatePV. Обратите внимание, как столбцы имеют эту DBCOLUMNFLAGS_ISNULLABLE для недействительных столбцов.

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

Как и в случае с данными NULL, вы несете ответственность за изменение значений по умолчанию.

По `FlushData` умолчанию `Execute` и заключается в том, чтобы вернуть S_OK. Поэтому, если вы не отмените эту функцию, изменения, как представляется, увенчаются успехом (S_OK будут возвращены), но они не будут переданы в хранилище данных.

В `UpdatePV` выборке (в `SetDBStatus` Rowset.h) метод обрабатывает значения по умолчанию следующим образом:

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

### <a name="column-flags"></a>Флаги колонн

Если вы поддерживаете значения по умолчанию в столбцах, необходимо \<установить их с помощью метаданных в классе поставщиков\>SchemaRowset класса. Задайте `m_bColumnHasDefault = VARIANT_TRUE`.

Вы также несете ответственность за установку флагов колонн, которые указаны с помощью перечисленного типа DBCOLUMNFLAGS. Флаги колонны описывают характеристики колонны.

Например, в `CUpdateSessionColSchemaRowset` классе `UpdatePV` в (в Session.h) первая колонка настроена таким образом:

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

Этот код определяет, среди прочего, что столбец поддерживает значение по умолчанию 0, что он может быть записываемым, и что все данные в столбце имеют одинаковую длину. Если вы хотите, чтобы данные в столбце имели переменную длину, этот флаг не устанавливал.

## <a name="see-also"></a>См. также раздел

[Создание поставщика OLE DB](creating-an-ole-db-provider.md)
