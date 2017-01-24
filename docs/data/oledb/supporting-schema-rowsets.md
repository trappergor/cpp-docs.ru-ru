---
title: "Поддержка наборов строк схемы | Microsoft Docs"
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
  - "шаблоны потребителя OLE DB, наборы строк схемы"
  - "поставщики OLE DB, наборы строк схемы"
  - "OLE DB, наборы строк схемы"
  - "наборы строк схемы"
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Поддержка наборов строк схемы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Наборы строк схемы позволяют пользователям получать информацию о хранилище данных, не раскрывая его базовой структуры или схемы.  Например, в хранилище данных могут содержаться таблицы, упорядоченные в пользовательскую иерархию, таким образом, невозможно получить сведения о схеме, непосредственно не ознакомившись с ней \(в качестве другого примера отметим также, что мастера Visual C\+\+ используют наборы строк схемы для создания методов доступа для пользователей\). С целью предоставления доступа объект сеанса поставщика представляет методы в интерфейсе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx).  В приложениях Visual C\+\+ для реализации **IDBSchemaRowset** используется класс [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md).  
  
 `IDBSchemaRowsetImpl` поддерживает следующие методы:  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) проверяет допустимость ограничений в наборе строк схемы.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) реализует функцию создания COM\-объекта для объекта, указанного в параметре шаблона.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) указывает на ограничения, поддерживаемые в определенном наборе строк схемы.  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) возвращает набор строк схемы \(унаследованный от интерфейса\).  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) возвращает список наборов строк схемы, доступный через `IDBSchemaRowsetImpl::GetRowset` \(унаследованный от интерфейса\).  
  
## Поддержка мастера поставщиков OLE DB библиотеки ATL  
 Мастер поставщиков OLE DB библиотеки ATL создает три класса схемы в файле заголовка сеанса.  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 Эти классы отвечают на запросы объекта\-получателя о сведениях про схему; следует также учитывать, что спецификации OLE DB требуют поддержки следующих наборов строк схемы:  
  
-   **C** *ShortName* **SessionTRSchemaRowset** обрабатывает запросы на информацию из таблицы \(набор строк схемы `DBSCHEMA_TABLES`\).  
  
-   **C** *ShortName* **SessionColSchemaRowset** обрабатывает запросы на информацию из столбца \(набор строк схемы **DBSCHEMA\_COLUMNS**\).  Мастер предоставляет образцы реализации этих классов, которые возвращают информацию о схеме для поставщика DOS.  
  
-   **C** *ShortName* **SessionPTSchemaRowset** обрабатывает запросы на информацию о схеме, касающуюся типа поставщика \(набор строк схемы **DBSCHEMA\_PROVIDER\_TYPES**\).  По умолчанию предоставленная мастером реализация возвращает `S_OK`.  
  
 Достичь соответствия схемы информации поставщику можно в результате соответствующих настроек.  
  
-   В **C***ShortName***SessionTRSchemaRowset** необходимо заполнять каталог, таблицу и поля описания \(**trData.m\_szType**, **trData.m\_szTable** и **trData.m\_szDesc**\).  В примере мастера используется только один ряд \(таблица\).  Другие поставщики могут возвращать более одной таблицы.  
  
-   В **C***ShortName***SessionColSchemaRowset** имя таблицы передается как **DBID**.  
  
## Ограничения параметров  
 Важным принципом в поддержке набора строк схемы является ограничение параметров, устанавливаемых с помощью `SetRestrictions`.  Ограничения позволяют пользователям выбирать только соответствующие строки \(например, находить все столбцы в таблице "MyTable"\).  Ограничения не являются обязательными; в случае если ни одно их них не поддерживается \(по умолчанию\), осуществляется возврат всех данных.  Пример поставщика, не поддерживающего ограничения, см. в образце [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
## Установка схемы карт  
 Можно установить схему карт, как показано в примере Session.h в UpdatePV:  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 Для поддержки **IDBSchemaRowset** необходимо обеспечить поддержку `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** и **DBSCHEMA\_PROVIDER\_TYPES**.  По необходимости могут добавляться дополнительные наборы строк схем.  
  
 Объявите класс набора строк схем с методом `Execute`, также как `CUpdateSessionTRSchemaRowset` — в UpdatePV:  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 Следует учитывать, что `CUpdateSession` унаследован от `IDBSchemaRowsetImpl`, поэтому он поддерживает все методы обработки ограничений.  Использование `CSchemaRowsetImpl` объявляет три дочерних класса \(перечислены на схеме карт выше\): `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset` и `CUpdateSessionPTSchemaRowset`.  Каждый из дочерних классов имеет метод `Execute`, который обрабатывает соответствующий набор ограничений \(критерии поиска\).  Каждый метод `Execute` сравнивает значения `cRestrictions` и параметры `rgRestrictions`.  Описание этих параметров см. в разделе [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
 Дополнительные сведения об ограничениях, соответствующих определенному набору строк схемы, см. в таблице наборов строк схемы GUID в [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx), *OLE DB Programmer's Reference*, [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 Например, при поддержке ограничений **TABLE\_NAME** в `DBSCHEMA_TABLES` можно выполнить следующее.  
  
 Произвести поиск `DBSCHEMA_TABLES` и убедится в том, что таблицы поддерживают \(контролируют\) четыре ограничения.  
  
|Ограничение набора строк схемы|Значение ограничения|  
|------------------------------------|--------------------------|  
|**TABLE\_CATALOG**|0x1 \(двоичный 1\)|  
|**TABLE\_SCHEMA**|0x2 \(двоичный 10\)|  
|**TABLE\_NAME**|0x4 \(двоичный 100\)|  
|**TABLE\_TYPE**|0x8 \(двоичный 1000\)|  
  
 Далее обратите внимание, что на каждое ограничение приходится по одному биту.  Чтобы обеспечить поддержку исключительно **TABLE\_NAME**, необходим возврат 0x4 в элементе `rgRestrictions`.  При поддержке **TABLE\_CATALOG** и **TABLE\_NAME** необходим возврат 0x5 \(двоичный 101\).  
  
 По умолчанию на все запросы реализация возвращает 0 \(не поддерживает ограничения\).  UpdatePV является примером поставщика, не поддерживающего ограничения.  
  
### Пример  
 Код взят из образца [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f).  UpdatePv поддерживает три обязательных набора строк схемы: `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** и **DBSCHEMA\_PROVIDER\_TYPES**.  В качестве примера реализации поддержки схемы в поставщике здесь описывается реализация набора строк **DBSCHEMA\_TABLE**.  
  
> [!NOTE]
>  Образец кода может отличаться от приведенного в примере; рассматривать образец кода следует как более современную версию.  
  
 Первой задачей при добавлении поддержки схемы является определение ограничений, которым будет предоставляться поддержка.  Чтобы определить ограничения, доступные для набора строк схемы, необходимо выполнить поиск спецификаций OLE DB для определения **IDBSchemaRowset**.  Согласно основному определению в отображенной таблице указывается имя набора строк схемы, количество и столбцы ограничений.  Выберите набор строк схемы, которому будет предоставляться поддержка, с учетом количества и столбцов ограничений.  Например, `DBSCHEMA_TABLES` поддерживает четыре ограничения \(**TABLE\_CATALOG**, **TABLE\_SCHEMA**, **TABLE\_NAME** и **TABLE\_TYPE**\).  
  
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
  
 Бит представляет каждый столбец ограничений.  При необходимости поддержки ограничения \(т. е. возможности запроса на ограничение\) для бита устанавливается значение 1.  Чтобы не поддерживать ограничение, для бита устанавливается значение 0.  Поддержка ограничений **TABLE\_NAME** и **TABLE\_TYPE** UpdatePV в наборе строк `DBSCHEMA_TABLES` осуществляется в указанной выше строке кода.  Это третье \(битовая маска 100\) и четвертое \(битовая маска 1000\) ограничения.  Таким образом, битовая маска для UpdatePv – 1100 \(или 0x0C\):  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 Следующая функция `Execute` подобна функциям в обычных наборах строк.  Существуют следующие три аргумента: `pcRowsAffected`, `cRestrictions` и `rgRestrictions`.  Переменная `pcRowsAffected` является выходным параметром, с помощью которого поставщик может возвращать количество строк в наборе строк схемы.  Параметр `cRestrictions` является входным параметром, содержащим количество ограничений, переданных объектом\-получателем поставщику.  Параметр `rgRestrictions` является массивом значений **VARIANT**, содержащим значения ограничений.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 Переменная `cRestrictions` основывается на общем количестве ограничений для набора строк схемы, независимо от поддержки поставщика.  Поскольку UpdatePv поддерживает два ограничения \(третье и четвертое\), этот код осуществляет только поиск значения `cRestrictions`, превышающего или равного трем.  
  
 Значение для ограничения **TABLE\_NAME** сохраняется в `rgRestrictions[2]` \(при этом третье ограничение с индексацией от нуля составляет 2\).  Чтобы гарантировать поддержку, необходимо убедиться в том, что ограничение не является `VT_EMPTY`.  Обратите внимание, что значение **VT\_NULL** не равно значению `VT_EMPTY`.  **VT\_NULL** указывает на действительное значение ограничения.  
  
 Определение UpdatePv названия таблицы представляет собой полный путь к текстовому файлу.  Убедиться в том, что файл не существует, можно посредством извлечения значений ограничения и открытия файла.  Если файл не существует, следует осуществить возврат `S_OK`.  Эта операция может напоминать возврат бита, однако, основной функцией кода является сообщение объекту\-получателю о том, что таблицы, соответствующие указанному имени, не найдены.  Возврат `S_OK` означает правильность выполнения кода.  
  
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
  
 Поддержка четвертого ограничения \(**TABLE\_TYPE**\) подобна третьему ограничению.  Убедитесь в том, что значение не равно `VT_EMPTY`.  Это ограничение лишь возвращает тип таблицы **TABLE**.  Чтобы определить допустимые значения для `DBSCHEMA_TABLES`, см. приложение Б *справочника программиста по OLE DB*, подраздел про набор строк **TABLES**.  
  
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
  
 Это место фактического ввода строк в набор строк.  Переменная `trData` соответствует **CTABLESRow**, структуре, определенной в шаблонах поставщика OLE DB.  **CTABLESRow** соответствует определению набора строк **TABLES** в приложении Б спецификации OLE DB.  Поскольку одновременно может осуществляться поддержка только одной таблицы, за один раз можно добавить только одну строку.  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  
wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  
wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV устанавливает только три столбца: **TABLE\_NAME**, **TABLE\_TYPE** и **DESCRIPTION**.  Следует помечать столбцы, для которых осуществляется возврат информации, поскольку эта информация используется во время реализации `GetDBStatus`.  
  
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
  
 Функция `GetDBStatus` необходима для правильного выполнения набора строк схемы.  Поскольку данные возвращаются не для каждого столбца в наборе строк **TABLES**, необходимо указывать столбцы, для которых осуществляется и для которых не осуществляется возврат данных.  
  
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
  
 Поскольку функция `Execute` возвращает данные для полей **TABLE\_NAME**, **TABLE\_TYPE** и **DESCRIPTION** из набора строк **TABLES**, в приложении Б спецификации OLE DB можно определить \(посчитав сверху вниз\), что эти столбцы представлены порядковыми числами 3, 4 и 6.  Для каждого из этих столбцов следует возвратить **DBSTATUS\_S\_OK**.  Для остальных столбцов осуществляется возврат **DBSTATUS\_S\_ISNULL**.  Необходимо возвращать запросы состояния, поскольку объект\-получатель может не предполагать, что возвращаемое значение — **NULL** или подобное.  Еще раз следует обратить внимание на то, что значение **NULL** и пустое значение не эквивалентны.  
  
 Дополнительные сведения про интерфейс набора строк схемы OLE DB см. в интерфейсе [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) справочника программиста по OLE DB.  
  
 Дополнительные сведения про способы использования объектами\-получателями методов **IDBSchemaRowset** см. в разделе [Получение метаданных с помощью наборов строк схемы](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).  
  
 Пример поставщика, поддерживающего наборы строк схемы, см. в примере [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
## См. также  
 [Дополнительные способы использования поставщика](../Topic/Advanced%20Provider%20Techniques.md)