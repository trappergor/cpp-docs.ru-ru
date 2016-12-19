---
title: "Создание поставщика с возможностью записи | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "уведомления, поддержка поставщиков"
  - "поставщики OLE DB, создание"
  - "поставщики OLE DB, обновляемые"
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание поставщика с возможностью записи
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В Visual C\+\+ 6.0 поддерживались только поставщики, позволяющие только считывать данные.  В Visual C\+\+ .NET поддерживаются поставщики, которые могут обновлять хранилище данных \(записывать в него данные\).  Этот раздел посвящен созданию поставщиков с возможностью записи с помощью шаблонов OLE DB.  
  
 В этом разделе предполагается, что используется рабочий поставщик.  Для создания поставщика с возможностью записи необходимо выполнить два шага.  Сначала следует решить, как поставщик должен вносить изменения в хранилище данных, а именно, требуется ли применять изменения незамедлительно или после получения команды обновления.  В разделе "[Создание поставщиков с возможностью записи](#vchowmakingprovidersupdatable)" описаны необходимые изменения и параметры, которые следует внести в код поставщика.  
  
 Затем необходимо убедиться, что поставщик обладает всеми функциями для поддержки любых запросов пользователя.  Если пользователь хочет обновить хранилище данных, в поставщике должен содержаться код, сохраняющий данные в хранилище.  Например, для выполнения подобных операций над источником данных можно использовать библиотеку среды выполнения C или MFC.  В разделе "[Запись в источник данных](#vchowwritingtothedatasource)" описывается, как записывать данные в источник данных, обрабатывать значение **NULL** и значения по умолчанию, а также устанавливать флаги столбцов.  
  
> [!NOTE]
>  UpdatePV — это пример поставщика с возможностью записи.  UpdatePV аналогичен MyProv, только в нем поддерживается возможность записи.  
  
##  <a name="vchowmakingprovidersupdatable"></a> Создание поставщиков с возможностью записи  
 Ключом к созданию поставщиков с возможностью записи является понимание того, какие операции должен выполнять поставщик с хранилищем данных и каким образом он должен это делать.  Так, основной вопрос заключается в том, должно ли хранилище данных обновляться незамедлительно или после получения команды обновления.  
  
 Для начала необходимо решить, следует ли наследовать класс набора строк от класса `IRowsetChangeImpl` или класса `IRowsetUpdateImpl`.  В зависимости от выбранного класса затрагивается функциональность трех методов: `SetData`, **InsertRows** и `DeleteRows`.  
  
-   При наследовании от класса [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md) вызов этих трех методов приводит к незамедлительному изменению хранилища данных.  
  
-   При наследовании от класса [IRowsetUpdateImpl](../Topic/IRowsetUpdateImpl%20Class.md) хранилище данных будет изменено только после вызова метода **Update**, `GetOriginalData` или **Undo**.  Если обновление означает несколько изменений, они выполняются в пакетном режиме \(обратите внимание, что изменения в пакетном режиме могут привести к значительному увеличению используемой памяти\).  
  
 Обратите внимание, что класс `IRowsetUpdateImpl` является производным от класса `IRowsetChangeImpl`.  Поэтому класс `IRowsetUpdateImpl` предоставляет возможности записи в хранилище данных, а также возможность внесения изменений в пакетном режиме.  
  
#### Чтобы поставщик поддерживал возможность записи, необходимо выполнить следующие действия.  
  
1.  В классе набора строк наследуйте от класса `IRowsetChangeImpl` или `IRowsetUpdateImpl`.  Эти классы обеспечивают необходимые интерфейсы для изменения хранилища данных.  
  
     **Добавление IRowsetChange**  
  
     Добавьте `IRowsetChangeImpl` в цепочку наследования с помощью следующей формы:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Также добавьте `COM_INTERFACE_ENTRY(IRowsetChange)` в раздел `BEGIN_COM_MAP` класса набора строк.  
  
     **Добавление IRowsetUpdate**  
  
     Добавьте `IRowsetUpdate` в цепочку наследования с помощью следующей формы:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Следует удалить строку `IRowsetChangeImpl` из цепочки наследования.  В это исключение для упомянутой выше директивы необходимо включить код для реализации класса `IRowsetChangeImpl`.  
  
2.  Добавьте описанные ниже элементы в сопоставление COM \(**BEGIN\_COM\_MAP ... END\_COM\_MAP**\).  
  
    |Реализация|Элемент, добавляемый к сопоставлению COM|  
    |----------------|----------------------------------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  В команде добавьте описанные ниже элементы в сопоставление набора свойств \(**BEGIN\_PROPSET\_MAP ... END\_PROPSET\_MAP**\).  
  
    |Реализация|Элемент, добавляемый к сопоставлению набора свойств|  
    |----------------|---------------------------------------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  В сопоставление набора свойств также необходимо включить все следующие параметры, в форме представленной ниже:  
  
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
  
     Значения, используемые при вызове этих макросов, можно найти, просмотрев в файле Atldb.h идентификаторы свойств и их значения \(если Atldb.h отличается от документации в Интернете, то файл Atldb.h замещает ее\).  
  
    > [!NOTE]
    >  Многие из параметров **VARIANT\_FALSE** и `VARIANT_TRUE` необходимы для использования шаблонов OLE DB; в спецификации OLE DB говорится, что параметры доступны для чтения и записи, но шаблоны OLE DB могут поддерживать только одно значение.  
  
     **Реализация класса IRowsetChangeImpl**  
  
     При реализации класса `IRowsetChangeImpl` в поставщике необходимо задать значения следующих свойств.  Эти свойства в основном используются для запроса данных у интерфейсов с помощью метода **ICommandProperties::SetProperties**.  
  
    -   `DBPROP_IRowsetChange`: при задании этого свойства **DBPROP\_IRowsetChange** устанавливается автоматически.  
  
    -   `DBPROP_UPDATABILITY`: битовая маска, указывающая поддерживаемые методы в классе `IRowsetChange`: `SetData`, `DeleteRows` или `InsertRow`.  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: объект\-получатель может вызвать метод **IRowsetChange::DeleteRows** или `SetData` для получения только что вставленных строк.  
  
    -   `DBPROP_IMMOBILEROWS`: набор строк не будет переупорядочивать вставленные или обновленные строки.  
  
     **Реализация класса IRowsetUpdateImpl**  
  
     При реализации класса `IRowsetUpdateImpl` в поставщике необходимо присвоить значения следующим свойствам, помимо всех вышеперечисленных свойств класса `IRowsetChangeImpl`:  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT`: значение должно быть равно READ\_ONLY AND VARIANT\_TRUE.  
  
    -   `DBPROP_OWNUPDATEDELETE`: значение должно быть равно READ\_ONLY AND VARIANT\_TRUE.  
  
    -   `DBPROP_OTHERINSERT`: значение должно быть равно READ\_ONLY AND VARIANT\_TRUE.  
  
    -   `DBPROP_OTHERUPDATEDELETE`: значение должно быть равно READ\_ONLY AND VARIANT\_TRUE.  
  
    -   `DBPROP_REMOVEDELETED`: значение должно быть равно READ\_ONLY AND VARIANT\_TRUE.  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  Если требуется поддержка уведомлений, также необходимо задать некоторые другие свойства; список дополнительных свойств см. в разделе `IRowsetNotifyCP`.  
  
     Пример присвоения значений свойствам см. в сопоставлении набора свойств **CUpdateCommand** \(в файле Rowset.h\) в разделе [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
##  <a name="vchowwritingtothedatasource"></a> Запись в источник данных  
 Для считывания данных из источника данных следует вызвать функцию **Execute**.  Для записи данных в источник данных следует использовать функцию `FlushData`. \(В общем смысле "flush" \(очистка\) означает сохранение изменений таблицы или индекса на диск\).  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 Аргументы дескриптора строки \(*HROW*\) и дескриптора метода доступа \(*HACCESSOR*\) позволяют задать область записи.  Обычно за один раз записывается одно поле данных.  
  
 Метод `FlushData` записывает данные в формате, в котором они первоначально хранились.  Если эта функция не переопределяется, поставщик работает корректно, но изменения не вносятся в хранилище данных.  
  
### Условия записи данных  
 Шаблоны поставщика вызывают метод `FlushData`, когда необходимо записать данные в хранилище данных, что обычно \(но не всегда\) происходит при вызове следующих функций:  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** \(если существуют новые данные, которые необходимо вставить в строку\)  
  
-   **IRowsetUpdate::Update**  
  
### Принцип работы  
 Объект\-получатель вызывает метод, требующий обновления данных \(например, **Update**\) и этот вызов передается поставщику, который всегда совершает следующие действия.  
  
-   Вызывает метод `SetDBStatus`, если используется привязка к значению состояния \(см. *справочник программиста OLE DB*, главу 6, *Части данных: состояние*\).  
  
-   Проверяет флаги столбца.  
  
-   Вызывает `IsUpdateAllowed`.  
  
 Эти три шага обеспечивают безопасность.  Затем поставщик вызывает метод `FlushData`.  
  
### Реализация метода FlushData  
 При реализации метода `FlushData` необходимо учитывать несколько вопросов.  
  
-   Необходимо убедиться, что хранилище данных может обрабатывать изменения.  
  
-   Необходимо обрабатывать значения **NULL**.  
  
-   Необходимо обрабатывать значения по умолчанию.  
  
 Для реализации собственного метода `FlushData` следует выполнить следующие действия.  
  
-   Перейти к классу набора строк.  
  
-   В класс набора строк поместить следующее объявление:  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   Предоставить реализацию метода `FlushData`.  
  
 Рекомендуется, чтобы метод `FlushData` сохранял только обновляемые строки и столбцы.  Для определения текущей сохраняемой строки и текущего сохраняемого столбца в целях оптимизации можно использовать параметры *HROW* и *HACCESSOR*.  
  
 Обычно самая большие трудности возникают с собственным неуправляемым хранилищем данных.  По возможности выполните следующие рекомендации.  
  
-   Постарайтесь реализовать метод записи в хранилище данных как можно проще.  
  
-   Обрабатывайте значения **NULL** \(необязательно, но желательно\).  
  
-   Обрабатывайте значения по умолчанию \(необязательно, но желательно\).  
  
 Лучший способ — хранить фактические значения в хранилище данных для значений **NULL** и значений по умолчанию.  Этот метод лучше всего использовать, если данные можно экстраполировать.  В противном случае рекомендуется запретить использование значений **NULL** и значений по умолчанию.  
  
 В следующем примере показано, как метод `FlushData` реализован в классе `RUpdateRowset` в примере [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f) \(см. файл Rowset.h в примере кода\):  
  
```  
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
  
### Обработка изменений  
 Чтобы поставщик обрабатывал изменения, необходимо убедиться, что хранилище данных \(текстовый файл или видеофайл\) обладает средствами для применения изменений.  В противном случае следует создать подобный код отдельно от проекта поставщика.  
  
### Обработка значений NULL  
 Возможно, что конечный пользователь отправит значения **NULL** в качестве данных.  При записи значений **NULL** в поля источника данных могут возникнуть проблемы.  Допустим, приложение, обрабатывающее заказы, принимает значения, обозначающие город и почтовый индекс. Приложение может принять одно из значений или оба значения, но отсутствие хотя бы одного из них будет означать невозможность доставки.  Поэтому необходимо сделать ограничения для определенных сочетаний значений **NULL** для полей, соответствующих конкретному приложению.  
  
 Разработчик поставщика должен учитывать способ хранения и чтения данных из хранилища, а также способ уведомления пользователя.  Так, необходимо учитывать способ изменения состояния данных набора строк в источнике данных \(например, DataStatus \= **NULL**\).  Следует решить, какое значение возвращается, когда объект\-получатель обращается к полю, содержащему значение **NULL**.  
  
 В примере кода [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f) показано, как поставщик может обрабатывать значения **NULL**.  В этом примере поставщик сохраняет значения **NULL**, записывая строку "NULL" в хранилище данных.  При считывании значений **NULL** из хранилища поставщик видит эту строку, очищает буфер и создает строку **NULL**.  Также в поставщике есть переопределение метода `IRowsetImpl::GetDBStatus`, в котором возвращается значение **DBSTATUS\_S\_ISNULL**, если значение данных пустое.  
  
### Выделение столбцов со значением NULL  
 При реализации набора строк схемы \(см. описание метода `IDBSchemaRowsetImpl`\) в реализации необходимо указать в наборе строк **DBSCHEMA\_COLUMNS** \(обычно отмеченном в поставщике как **C***xxx***SchemaColSchemaRowset**\) то, что столбец может содержать значения NULL.  
  
 Также необходимо указать, что все подобные столбцы содержат значение **DBCOLUMNFLAGS\_ISNULLABLE** в собственной версии `GetColumnInfo`.  
  
 При реализации шаблонов OLE DB, если не удается выделить столбцы, которые могут содержать значение NULL, поставщик предполагает, что они содержат значение, и не позволяет объекту\-получателю отправлять значения NULL.  
  
 В следующем примере показано, как функция **CommonGetColInfo** реализована в **CUpdateCommand** \(см. файл UpProvRS.cpp\) в примере UpdatePV.  Следует заметить, что в пустых столбцах в этом примере содержится значение **DBCOLUMNFLAGS\_ISNULLABLE**.  
  
```  
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
  
### Значения по умолчанию  
 Как и в случае со значениями **NULL**, также необходимо обрабатывать изменения значений по умолчанию.  
  
 По умолчанию методы `FlushData` и **Execute** возвращают значение `S_OK`.  Поэтому, если эта функция не переопределяется, кажется, что изменения успешно применяются \(возвращается значение `S_OK`\), но измененные значения не передаются в хранилище данных.  
  
 В примере кода [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f) \(в файле Rowset.h\) метод `SetDBStatus` обрабатывает значения по умолчанию следующим образом:  
  
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
  
### Флаги столбцов  
 Если требуется поддержка значений по умолчанию для столбцов, необходимо задать ее, используя метаданные класса **\>SchemaRowset***класса поставщика***\<**.  Задайте *m\_bColumnHasDefault* \= `VARIANT_TRUE`.  
  
 Также необходимо установить флаги столбцов, которые указываются с помощью перечисляемого типа **DBCOLUMNFLAGS**.  Флаги столбцов описывают характеристики столбца.  
  
 Например, в классе `CUpdateSessionColSchemaRowset` в [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f) \(в файле Session.h\), флаги первого столбца заданы следующим образом:  
  
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
  
 В этом коде, помимо прочего, указано, что столбец поддерживает значение по умолчанию, равное 0, что столбец доступен для записи и что все данные в столбце одинаковой длины.  Если данные в столбце различной длины, этот флаг не надо устанавливать.  
  
## См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)