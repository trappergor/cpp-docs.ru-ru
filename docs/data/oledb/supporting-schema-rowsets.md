---
title: Поддержка наборов строк схемы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 95f1455fde75ec835486cbcc3d590822891d14f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111761"
---
# <a name="supporting-schema-rowsets"></a>Поддержка наборов строк схемы
Наборы строк схемы позволяют пользователям получать информацию о хранилище данных, не зная ее базовую структуру или схему. Например хранилище данных может иметь таблицы, упорядоченные в пользовательской иерархии, поэтому будет гарантировать знаний о схеме, считывая его. (Еще один пример, обратите внимание, что мастера Visual C++ используйте наборы строк схемы для создания методов доступа для пользователя.) Чтобы разрешить пользователю для этого, объект сеанса поставщика представляет методы на [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) интерфейса. В приложениях Visual C++ используйте [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) класса для реализации **IDBSchemaRowset**.  
  
 `IDBSchemaRowsetImpl` поддерживает следующие методы:  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) проверяет допустимость ограничений относительно набора строк схемы.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) указывает на ограничения, поддерживаемые в определенном наборе строк схемы.  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) возвращает набор строк схемы (наследуется от интерфейса).  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) возвращает список наборов строк схемы, доступных для `IDBSchemaRowsetImpl::GetRowset` (наследуется от интерфейса).  
  
## <a name="atl-ole-db-provider-wizard-support"></a>Поддержка ATL OLE DB Provider мастера  
 Мастер поставщика ATL OLE DB создает три класса схемы в файле заголовка сеанса:  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 Эти классы отвечают на запросы потребителя сведений о схеме; Обратите внимание, что спецификация OLE DB требует поддержки следующих наборов строк схемы.  
  
-   **C** *ShortName* **SessionTRSchemaRowset** обрабатывает запросы сведений о таблице ( `DBSCHEMA_TABLES` набора строк схемы).  
  
-   **C** *ShortName* **SessionColSchemaRowset** обрабатывает запросы сведений о столбце ( **DBSCHEMA_COLUMNS** набора строк схемы). Мастер предоставляет образцы реализации этих классов, которые возвращают сведения о схеме для поставщика DOS.  
  
-   **C** *ShortName* **SessionPTSchemaRowset** обрабатывает запросы сведений схемы об тип поставщика ( **DBSCHEMA_PROVIDER_TYPES** схемы набор строк). Реализация по умолчанию, предоставляемого мастером возвращает `S_OK`.  
  
 Можно настроить эти классы для обработки сведений о схеме, подходящим для поставщика.  
  
-   В **C***ShortName***SessionTRSchemaRowset**, необходимо заполнить поля каталога, таблицы и описание (**trData.m_szType**, **trData.m_szTable** , и **trData.m_szDesc**). В примере мастера используется только один ряд (таблица). Другие поставщики могут возвращать более одной таблицы.  
  
-   В **C***ShortName***SessionColSchemaRowset**, вы передаете имя таблицы как **DBID**.  
  
## <a name="setting-restrictions"></a>Задание ограничений  
 Важным принципом в поддержке набора строк схемы является ограничение параметров, устанавливаемых с помощью `SetRestrictions`. Ограничения позволяют выбирать только совпадающие строки (например, поиск всех столбцов в таблице MyTable). Ограничения являются необязательными, и если не поддерживается ни одно ограничение (по умолчанию), всегда возвращаются все данные. Пример поставщика, поддерживающего ограничения см. в разделе [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) образца.  
  
## <a name="setting-up-the-schema-map"></a>Настройка сопоставления в схеме  
 Настройка сопоставления в схеме такой Session.h в этом примере:  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 Для поддержки **IDBSchemaRowset**, должны поддерживать `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, и **DBSCHEMA_PROVIDER_TYPES**. Можно добавить дополнительные наборы строк схем по своему усмотрению.  
  
 Объявление класса набора строк схемы с `Execute` метода, такие как `CUpdateSessionTRSchemaRowset` в этом примере:  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 Обратите внимание, что `CUpdateSession` наследует от `IDBSchemaRowsetImpl`, поэтому он поддерживает все методы обработки ограничений. С помощью `CSchemaRowsetImpl`, объявляет три дочерних класса (перечислены в схеме карт выше): `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset`, и `CUpdateSessionPTSchemaRowset`. Каждый из дочерних классов имеет `Execute` метод, который обрабатывает соответствующий набор ограничений (критерии поиска). Каждый `Execute` метод сравнивает значения `cRestrictions` и `rgRestrictions` параметров. См. в описании этих параметров [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
 Дополнительные сведения о том, какие ограничения соответствуют определенном наборе строк схемы, см. в таблице идентификаторов GUID набора строк схемы в [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *Справочник программиста OLE DB* в Пакет Windows SDK.  
  
 Например, если вы поддерживается **TABLE_NAME** ограничения на `DBSCHEMA_TABLES`, можно сделать следующее:  
  
 Во-первых, поиск `DBSCHEMA_TABLES` и увидеть, что он поддерживает четыре ограничения (в порядке).  
  
|Ограничение набора строк схемы|Значение ограничения|  
|-------------------------------|-----------------------|  
|**ЗНАЧЕНИЯМ TABLE_CATALOG**|0x1 (двоичный 1)|  
|**TABLE_SCHEMA**|0x2 (двоичный 10)|  
|**ИМЯ_ТАБЛИЦЫ**|0x4 (двоичный 100)|  
|**TABLE_TYPE**|0x8 (двоичный 1000)|  
  
 Далее Обратите внимание, что один бит для каждого ограничения. Так как вы собираетесь поддерживать **TABLE_NAME** только возврат 0x4 в `rgRestrictions` элемент. При поддержке **значениям TABLE_CATALOG** и **TABLE_NAME**, возвратят 0x5 (двоичный 101).  
  
 По умолчанию реализация возвращает 0 (не поддерживает ограничения) для любого запроса. UpdatePV является примером поставщика, который поддерживает ограничения.  
  
### <a name="example"></a>Пример  
 Этот код взят из [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) образца. UpdatePv поддерживает три наборы строк схемы, необходимый: `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, и **DBSCHEMA_PROVIDER_TYPES**. В качестве примера реализации поддержки схемы в поставщике, в этом разделе описывается реализация **DBSCHEMA_TABLE** набора строк.  
  
> [!NOTE]
>  Образец кода может отличаться от приведенного в примере; в образце кода следует рассматривать в качестве более позднюю версию.  
  
 Первым шагом при добавлении поддержки схемы является определение ограничений, которым будет добавлена поддержка. Чтобы определить ограничения, доступные для набора строк схемы, просмотрите спецификации OLE DB для определения **IDBSchemaRowset**. Согласно основному определению появиться таблица, содержащая имя набора строк схемы, число ограничений и столбцы ограничений. Выберите набор строк схемы, необходимые для поддержки и запомните или запишите число и столбцов ограничений. Например `DBSCHEMA_TABLES` поддерживает четыре ограничения (**значениям TABLE_CATALOG**, **TABLE_SCHEMA**, **TABLE_NAME**, и **TABLE_TYPE** ):  
  
```  
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,   
   ULONG* rgRestrictions)  
{  
    for (ULONG l=0; l<cRestrictions; l++)  
    {  
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
            rgRestrictions[l] = 0x0C;  
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))  
                 rgRestrictions[l] = 0x04;  
             else if (InlineIsEqualGUID(rguidSchema[l],  
                                        DBSCHEMA_PROVIDER_TYPES))  
                      rgRestrictions[l] = 0x00;  
   }  
}  
```  
  
 Бит представляет каждый столбец ограничений. Если вы хотите поддерживать ограничение (то есть, можно создавать запросы с его), значение бита 1. Если вы не хотите поддерживать ограничение, нулевое значение бита. В строке выше код UpdatePV поддерживает **TABLE_NAME** и **TABLE_TYPE** ограничения на `DBSCHEMA_TABLES` набора строк. Это третье (Битовая маска 100) и четвертой ограничения (Битовая маска 1000). Таким образом Битовая маска для UpdatePv — 1100 (или 0x0C):  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 Следующие `Execute` функция работает как в обычных наборах строк. У вас есть три аргумента: `pcRowsAffected`, `cRestrictions`, и `rgRestrictions`. `pcRowsAffected` Переменной является выходным параметром, что поставщик может возвращать количество строк в наборе строк схемы. `cRestrictions` Параметр является входным параметром, содержащим количество ограничений, переданных потребителем поставщику. `rgRestrictions` Параметр представляет собой массив **VARIANT** значений, содержащих значения ограничений.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions` Переменной основан на общее количество ограничений для набора строк схемы, независимо от того, поддерживаемых поставщиком. Поскольку UpdatePv поддерживает два ограничения (третье и четвертое), этот код осуществляет только поиск `cRestrictions` значения, большего или равного трем.  
  
 Значение для **TABLE_NAME** ограничение хранится в `rgRestrictions[2]` (, третье ограничение с индексацией составляет 2). Необходимо проверить, что ограничение не является `VT_EMPTY` чтобы гарантировать поддержку. Обратите внимание, что **VT_NULL** не равно `VT_EMPTY`. **VT_NULL** указывает на действительное значение ограничения.  
  
 Определение UpdatePv имени таблицы является полным путем к файлу в текстовый файл. Извлеките значение ограничения, а затем попытаться открыть файл, чтобы убедиться, что файл существует. Если файл не существует, возвращает `S_OK`. Это может показаться немного вперед, но действительно указывает, какой код потребителя является то, что существуют таблицы не поддерживается, соответствующие указанному имени. `S_OK` Возврата означает, что код выполняется неправильно.  
  
```  
USES_CONVERSION;  
enum {  
            sizeOfszFile = 255  
};  
CTABLESRow  trData;  
FILE        *pFile = NULL;  
TCHAR       szFile[ sizeOfszFile ];  
errcode     err = 0;  
  
// Handle any restrictions sent to us. This only handles  
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th   
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets   
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04   
// for a total of (0x0C)  
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)  
{  
    CComBSTR bstrName = rgRestrictions[2].bstrVal;  
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))  
    {  
        // Check to see if the file exists  
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));  
        if (szFile[0] == _T('\0') ||   
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))  
        {  
            return S_OK;// Their restriction was invalid return no data  
        }  
        else  
        {  
            fclose(pFile);  
        }  
    }  
}  
```  
  
 Поддержка четвертого ограничения (**TABLE_TYPE**) похож на третий ограниченного использования программ. Убедитесь, что значение не `VT_EMPTY`. Это ограничение лишь возвращает тип таблицы **таблицы**. Чтобы определить допустимые значения для `DBSCHEMA_TABLES`, в приложении Б *Справочник программиста OLE DB* в **ТАБЛИЦ** раздел набора строк.  
  
```  
// TABLE_TYPE restriction:  
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)  
{  
    CComBSTR bstrType = rgRestrictions[3].bstrVal;  
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))  
    {  
        // This is kind of a blind restriction.  
        // This only actually supports  
        // TABLES so if you get anything else,   
        // just return an empty rowset.  
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)  
            return S_OK;  
    }  
}  
```  
  
 Это фактически создаются запись строк для набора строк. Переменная `trData` соответствует **CTABLESRow**, структура, определенная в шаблоны поставщика OLE DB. **CTABLESRow** соответствует **ТАБЛИЦ** определение набора строк в приложении Б спецификации OLE DB. Имеется только одна строка для добавления, поскольку одновременно может поддерживать только одну таблицу.  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV задает только три столбца: **TABLE_NAME**, **TABLE_TYPE**, и **описание**. Следует помечать столбцы, для которых осуществляется возврат информации, поскольку эти сведения понадобятся при реализации `GetDBStatus`:  
  
```  
    _ATLTRY  
    {  
        m_rgRowData.Add(trData);  
    }  
    _ATLCATCHALL()  
    {  
        return E_OUTOFMEMORY;  
    }  
    //if (!m_rgRowData.Add(trData))  
    //    return E_OUTOFMEMORY;  
    *pcRowsAffected = 1;  
    return S_OK;  
}  
```  
  
 `GetDBStatus` Функции крайне важно для правильной работы набора строк схемы. Поскольку вы не возвращают данные для каждого столбца в **ТАБЛИЦ** набора строк, необходимо указать столбцы, которые возвращают данные, а какие нет.  
  
```  
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pColInfo != NULL);  
  
    switch(pColInfo->iOrdinal)  
    {  
    case 3:     // TABLE_NAME  
    case 4:     // TABLE_TYPE  
    case 6:     // DESCRIPTION  
        return DBSTATUS_S_OK;  
        break;  
    default:  
        return DBSTATUS_S_ISNULL;  
    break;  
    }  
}  
```  
  
 Так как ваш `Execute` функция возвращает данные для **TABLE_NAME**, **TABLE_TYPE**, и **описание** поля из **таблицы**набора строк, можно в приложении Б спецификации OLE DB и определить (с подсчетом сверху), порядковые номера, 3, 4 и 6. Для каждого из этих столбцов, вернуть **DBSTATUS_S_OK**. Для всех остальных столбцов, вернуть **DBSTATUS_S_ISNULL**. Очень важно для возврата состояния, так как объект-получатель может не понять, что возвращается значение является **NULL** либо другие. Обратите внимание, что **NULL** не эквивалентен пустым.  
  
 Дополнительные сведения про интерфейс набора строк схемы OLE DB см. в разделе [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) интерфейса в справочнике программиста OLE DB.  
  
 Сведения о том, как потребители могут использовать **IDBSchemaRowset** методов, см. [получение метаданных в схеме набора строк](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).  
  
 Пример поставщика, поддерживающего наборы строк схемы см. в разделе [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) образца.  
  
## <a name="see-also"></a>См. также  
 [Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)