---
title: "Создание поставщика с возможностью записи | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d65bce2b262b7582f9194eb8047d71ce06f3ca16
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="creating-an-updatable-provider"></a>Создание поставщика с возможностью записи
Visual C++ поддерживает поставщики, которые могут обновлять (запись) в хранилище данных. В этом разделе описывается создание обновляемых поставщиков с помощью шаблонов OLE DB.  
  
 Предполагается, что вы начинаете с рабочий поставщик. Существует два действия для создания поставщика с возможностью записи. Сначала необходимо решить, каким образом поставщик будут внесены изменения в хранилище данных; в частности изменения должны выполняться немедленно ли отложена, пока не будет выполнена команда обновления. Раздел «[Создание поставщиков с возможностью записи](#vchowmakingprovidersupdatable)» описаны изменения и параметры, необходимо внести в код поставщика.  
  
 Далее необходимо убедитесь, что поставщик содержит все функциональные возможности для поддержки любых потребитель может запросить его. Если необходимо обновить хранилище данных, поставщик должен содержать код, сохраняющий данные в хранилище данных. Например для выполнения таких операций в источнике данных могут использовать библиотеки времени выполнения C или MFC. Раздел «[запись в источнике данных](#vchowwritingtothedatasource)» описывает, как запись в источнике данных, как работать с **NULL** значения по умолчанию и установить флаги столбца.  
  
> [!NOTE]
>  UpdatePV является примером поставщика с возможностью записи. UpdatePV такое же, как поставщика MyProv, но с поддержкой обновляемых.  
  
##  <a name="vchowmakingprovidersupdatable"></a> Создание обновляемых поставщиков  
 Ключом к созданию поставщиков с обновляемым понимания того, какие операции требуется поставщиком для выполнения в хранилище данных, а также способ поставщика для выполнения этих операций. В частности, основной вопрос заключается в хранилище данных, установки обновлений для незамедлительно или отложена (объединены) пока не будет выполнена команда обновления.  
  
 Сначала необходимо решить, нужно ли наследовать от `IRowsetChangeImpl` или `IRowsetUpdateImpl` класса набора строк. В зависимости от того, какой из этих планируется реализовать, будут затронуты функциональные возможности из трех способов: `SetData`, **InsertRows**, и `DeleteRows`.  
  
-   При наследовании от [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), вызов этих трех методов немедленно изменению хранилища данных.  
  
-   При наследовании от [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), методы откладывания изменений в хранилище данных, пока не будет вызван **обновление**, `GetOriginalData`, или **отменить**. Если обновление затрагивает несколько изменений, они выполняются в пакетном режиме (Обратите внимание, что Пакетная обработка изменений можно добавить значительному увеличению используемой памяти).  
  
 Обратите внимание, что `IRowsetUpdateImpl` является производным от `IRowsetChangeImpl`. Таким образом `IRowsetUpdateImpl` предоставляет изменений возможностей, а также в пакетном режиме.  
  
#### <a name="to-support-updatability-in-your-provider"></a>Для поддержки возможности обновления в поставщике  
  
1.  В классе набора строк, наследуют `IRowsetChangeImpl` или `IRowsetUpdateImpl`. Эти классы обеспечивают необходимые интерфейсы для изменения хранилища данных:  
  
     **Добавление IRowsetChange**  
  
     Добавить `IRowsetChangeImpl` в цепочку наследования с помощью этой формы:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Кроме того, добавить `COM_INTERFACE_ENTRY(IRowsetChange)` для `BEGIN_COM_MAP` раздел класса набора строк.  
  
     **Добавление IRowsetUpdate**  
  
     Добавить `IRowsetUpdate` в цепочку наследования с помощью этой формы:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Следует удалить `IRowsetChangeImpl` строки из цепочки наследования. Это исключение для упомянутой выше директивы необходимо включить код для `IRowsetChangeImpl`.  
  
2.  Добавьте следующее сопоставление COM (**BEGIN_COM_MAP... END_COM_MAP**):  
  
    |При реализации|Добавить карту COM|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  В команде, добавьте следующее сопоставление набора свойств (**BEGIN_PROPSET_MAP... END_PROPSET_MAP**):  
  
    |При реализации|Добавьте сопоставление набора свойств|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  В сопоставление набора свойств следует также добавить все необходимые параметры, как они указаны ниже:  
  
    ```  
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
  
     Имеются значения, используемые в этих вызовов макросов путем поиска в Atldb.h идентификаторы свойств и их значения (если Atldb.h отличается от документации в Интернете, Atldb.h замещает ее).  
  
    > [!NOTE]
    >  Многие **VARIANT_FALSE** и `VARIANT_TRUE` требуются параметры, с помощью шаблонов OLE DB; спецификации OLE DB говорится, они могут быть чтения и записи, но шаблоны OLE DB поддерживает только одно значение.  
  
     **Если вы реализуете IRowsetChangeImpl**  
  
     Если вы реализуете `IRowsetChangeImpl`, необходимо задать следующие свойства для поставщика. Эти свойства в основном используются для запроса интерфейсов с помощью **ICommandProperties::SetProperties**.  
  
    -   `DBPROP_IRowsetChange`: Задание при этом автоматически задает **DBPROP_IRowsetChange**.  
  
    -   `DBPROP_UPDATABILITY`: Битовая маска, указывающая поддерживаемые методы на `IRowsetChange`: `SetData`, `DeleteRows`, или `InsertRow`.  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: Пользователь может вызвать **IRowsetChange::DeleteRows** или `SetData` для вставленных строк.  
  
    -   `DBPROP_IMMOBILEROWS`: Набор строк не будет переупорядочивать вставленные или обновленные строки.  
  
     **Если вы реализуете IRowsetUpdateImpl**  
  
     Если вы реализуете `IRowsetUpdateImpl`, необходимо задать следующие свойства для поставщика, кроме для задания свойств для `IRowsetChangeImpl` перечисленных выше:  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    -   `DBPROP_OWNUPDATEDELETE`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    -   `DBPROP_OTHERINSERT`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    -   `DBPROP_OTHERUPDATEDELETE`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    -   `DBPROP_REMOVEDELETED`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  Если требуется поддержка уведомлений, кроме того, возможны некоторые другие свойства также; см. в разделе `IRowsetNotifyCP` для этого списка.  
  
     Например из настроек свойств, см. свойство присвоения **значений свойствам** (в файле Rowset.h) в [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
##  <a name="vchowwritingtothedatasource"></a> Запись в источник данных  
 Для считывания из источника данных следует вызвать **Execute** функции. Чтобы записать в источник данных, вызовите `FlushData` функции. (В общем смысле диск означает сохранение изменений, внесенные в таблицы или индекса на диск).  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 Дескриптор строки (*HROW*) и дескриптора метода доступа (*HACCESSOR*) аргументы позволяют задать область записи. Как правило пишутся одного поля данных за раз.  
  
 `FlushData` Метод записывает данные в формате, в котором оно было изначально сохранено. Если эта функция не переопределяется, поставщик работает корректно, но изменения, не сбрасывается в хранилище данных.  
  
### <a name="when-to-flush"></a>Когда на диск  
 Шаблоны поставщика вызывают `FlushData` каждый раз, когда данные должны записываться в хранилище данных; это обычно (но не всегда) происходит в результате вызовов следующих функций:  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** (если нет новых данных для вставки в строке)  
  
-   **IRowsetUpdate::Update**  
  
### <a name="how-it-works"></a>Принцип работы  
 Потребитель вызывает метод, требующий обновления данных (таких как **обновление**) и этот вызов передается поставщику, который всегда выполняет следующее:  
  
-   Вызовы `SetDBStatus` каждый раз, когда у вас есть привязка к значению состояния (см. *справочнике программиста OLE DB*, Глава 6 *части данных: состояние*).  
  
-   Проверяет флаги столбца.  
  
-   Вызывает `IsUpdateAllowed`.  
  
 Эти три шага обеспечивают безопасность. Затем поставщик вызывает `FlushData`.  
  
### <a name="how-to-implement-flushdata"></a>Как реализовать FlushData  
 Для реализации `FlushData`, необходимо учитывать несколько вопросов:  
  
-   Убедившись, что хранилище данных может обрабатывать изменения.  
  
-   Обработка **NULL** значения.  
  
-   Обработка значений по умолчанию.  
  
 Для реализации собственного `FlushData` метод, необходимо:  
  
-   Перейти к классу набора строк.  
  
-   В наборе строк класса поместить следующее объявление:  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   Предоставляет реализацию `FlushData`.  
  
 Рекомендуется `FlushData` хранит только строки и столбцы, которые необходимо обновить. Можно использовать *HROW* и *HACCESSOR* параметры, чтобы определить текущую строку и столбец, сохраняемые для оптимизации.  
  
 Как правило самая сложная задача работает с хранилищем данных в собственном формате. Если это возможно попробуйте:  
  
-   Сохраните метод записи в хранилище данных как можно более простыми.  
  
-   Обрабатывать **NULL** значения (необязательно, но желательно).  
  
-   Обрабатывайте значения по умолчанию (необязательно, но желательно).  
  
 Лучший способ — хранить фактические значения в хранилище данных для **NULL** и значения по умолчанию. Проще всего, если эти данные можно экстраполировать. Если нет, рекомендуется не разрешить **NULL** и значения по умолчанию.  
  
 В следующем примере показан способ `FlushData` реализуется в `RUpdateRowset` класса в [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) образец (см. файл Rowset.h в образце кода):  
  
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
 Для поставщика для обработки изменений необходимо сначала убедитесь, что хранилище данных (например, текстовый файл или видеофайл) содержит средства, которые позволяют вносить изменения в нем. Если нет, этот код следует создавать отдельно от проекта поставщика.  
  
### <a name="handling-null-data"></a>Обработка значений NULL  
 Возможно, что конечный пользователь отправит **NULL** данных. При написании **NULL** значения для поля в источнике данных может быть потенциальных проблем. Представим себе приложение заказы, принимает значения для города и почтовый индекс. приложение может принять один или оба значения, но не ни одного, так как в этом случае будет невозможно доставки. Поэтому необходимо ограничить определенные сочетания **NULL** значений в полях, которые имеют смысл для вашего приложения.  
  
 Разработчик поставщика необходимо учитывать способ хранения данных, как будет считывать данные из хранилища данных и способ уведомления пользователя. В частности, необходимо учитывать способ изменения состояния данных набора строк в источнике данных (например, DataStatus = **NULL**). Решить, какое значение возвращается, когда получатель обращается к поле, содержащее **NULL** значение.  
  
 Посмотрите на код в [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) образец; здесь показано, как поставщик может обрабатывать **NULL** данных. В этом примере, поставщик хранит **NULL** данных, записывая строку «NULL» в хранилище данных. При считывании **NULL** хранилище данных на основе данных, он видит эту строку и очищает буфер, создание **NULL** строки. Она также содержит переопределение `IRowsetImpl::GetDBStatus` , в которой он возвращает **DBSTATUS_S_ISNULL** Если это значение данных пуст.  
  
### <a name="marking-nullable-columns"></a>Пометка столбцов со значением NULL  
 При реализации наборы строк схемы (см. `IDBSchemaRowsetImpl`), в реализации необходимо указать в **DBSCHEMA_COLUMNS** набора строк (обычно отмеченном в поставщике, **C***xxx*** SchemaColSchemaRowset**), является ли столбец значения NULL.  
  
 Необходимо также указать, что все столбцы, допускающие значения NULL содержать **DBCOLUMNFLAGS_ISNULLABLE** значения в версии `GetColumnInfo`.  
  
 В реализации шаблонов OLE DB Если не удается выделить столбцы, допускающие значение NULL, поставщик предполагает, что они должен содержать значение и не позволяет объекту-получателю отправлять значения null.  
  
 В следующем примере показан способ **CommonGetColInfo** функция реализована в **значений свойствам** (UpProvRS.cpp см) в этом примере. Обратите внимание, как столбцы это **DBCOLUMNFLAGS_ISNULLABLE** для столбцов со значением NULL.  
  
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
 Как и в **NULL** данных, также необходимо обрабатывать изменения значений по умолчанию.  
  
 Значение по умолчанию для `FlushData` и **Execute** возвращает `S_OK`. Таким образом, если эта функция не переопределяется, что изменения отображаются для успешного выполнения (`S_OK` будет возвращаться), но они не передаются в хранилище данных.  
  
 В [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) (в файле Rowset.h) `SetDBStatus` метод обрабатывает значения по умолчанию следующим образом:  
  
```  
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
 Если поддержка значений по умолчанию для столбцов, необходимо задать ее, используя метаданные  **\< ***класс поставщика***> SchemaRowset** класса. Задать *m_bColumnHasDefault* = `VARIANT_TRUE`.  
  
 Имеется также необходимо установить флаги столбцов, которые задаются с помощью **DBCOLUMNFLAGS** перечисляемый тип. Флаги столбцов описывают характеристики столбца.  
  
 Например, в `CUpdateSessionColSchemaRowset` класса в [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) (в Session.h), первый столбец заданы следующим образом:  
  
```  
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
  
 Этот код указывает, помимо прочего, что столбец поддерживает значение по умолчанию 0, что доступен для записи, и что все данные в столбце имеют одинаковую длину. Если требуется сохранить данные в столбце различной длины, этот флажок установлен не будет.  
  
## <a name="see-also"></a>См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)