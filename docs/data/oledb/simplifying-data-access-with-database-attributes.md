---
title: Упрощение доступа к данным с помощью атрибутов базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 10/19/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], database
- attributes [C++], data access
- databases [C++], attributes
- data [C++], simplifying access
- data access [C++], database attributes
- database attributes [C++]
- OLE DB consumers [C++], database attributes
- attributes [C++], OLE DB consumer
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2d5e141b71f5d78441438b825897868cd153b905
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079406"
---
# <a name="simplifying-data-access-with-database-attributes"></a>Упрощение доступа к данным с помощью атрибутов базы данных

В этом разделе демонстрируется использование атрибутов базы данных для упрощения операций базы данных.

Это простой способ доступа к информации из базы данных является создание класса команд (или таблиц) и класс записей пользователя для конкретной таблицы в базе данных. Атрибуты базы данных упрощают создание некоторых объявлений шаблонов, которые ранее требовалось выполнять.

Чтобы продемонстрировать использование атрибутов базы данных, в следующих разделах показано два эквивалентную таблицу и объявления класс записей пользователя: первый использует такие атрибуты, а второй использует шаблоны OLE DB. Такие объявления код обычно помещается в файл заголовка с именем для таблицы или объекта команды, например, Authors.h.

Сравнивая два файла, вы увидите, насколько проще является использование атрибутов. Различия включают:

- С помощью атрибутов, достаточно объявить один класс: `CAuthors`, тогда как с помощью шаблонов необходимо объявить два: `CAuthorsNoAttrAccessor` и `CAuthorsNoAttr`.

- `db_source` Вызов в версию эквивалентно `OpenDataSource()` вызова в объявлении шаблона.

- `db_table` Вызов в версию эквивалентно следующее объявление шаблона:

    ```cpp
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
    ```

- `db_column` Вызовы в версию эквивалентны в сопоставление столбцов (см. в разделе `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) в объявлении шаблона.

Эти атрибуты внедряют класс записей пользователя объявление для вас. Класс записей пользователя равен `CAuthorsNoAttrAccessor` в объявлении шаблона. Если класс таблицы `CAuthors`, пользовательский класс записи называется `CAuthorsAccessor`, и могут только просматривать ее объявления в подставляемый код. Дополнительные сведения см. в разделе «Классы записей пользователя см.в» в [записи пользователей](../../data/oledb/user-records.md).

Помеченные атрибутами и коде, необходимо задать свойства набора строк с помощью `CDBPropSet::AddProperty`.

Сведения об атрибутах, описанных в этом разделе, см. в разделе [атрибуты потребителя OLE DB](../../windows/ole-db-consumer-attributes.md).

> [!NOTE]
> Следующие `include` инструкций необходимых для компиляции в приведенных ниже примерах:
> ```cpp
> #include <atlbase.h>
> #include <atlplus.h>
> #include <atldbcli.h>
> ```

## <a name="table-and-accessor-declaration-using-attributes"></a>Таблицы и объявление метода доступа, с помощью атрибутов

Следующий код вызывает `db_source` и `db_table` в классе таблицы. `db_source` Указывает источник данных и подключение могло использоваться. `db_table` вставляет соответствующий код шаблона для объявления класса таблицы. `db_column` Укажите сопоставление столбцов и внедрить объявление метода доступа. Атрибуты потребителя OLE DB можно использовать в любом проекте, который поддерживает ATL.

Вот объявление метода доступа и таблицы, с помощью атрибутов:

```cpp
//////////////////////////////////////////////////////////////////////
// Table and accessor declaration using attributes
// authors.h
//////////////////////////////////////////////////////////////////////

// Table class declaration
// (Note that you must provide your own connection string for db_source.)
[
   db_source(L"your connection string"),
   db_table("Authors")
]
class CAuthors
{
public:
   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;
   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;
   [db_column("1", status = "m_dwAuIDStatus", length = "m_dwAuIDLength")] LONG m_AuID;
   [db_column("2", status = "m_dwAuthorStatus", length = "m_dwAuthorLength")] TCHAR m_Author[51];
   [db_column("3", status = "m_dwYearBornStatus", length = "m_dwYearBornLength")] SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
};
```

## <a name="table-and-accessor-declaration-using-templates"></a>Таблицы и объявление метода доступа, с помощью шаблонов

Ниже приведено объявление метода доступа и таблицы, с помощью шаблонов.

```cpp
//////////////////////////////////////////////////////////////////////
// Table and user record class declaration using templates
// authors.h
//////////////////////////////////////////////////////////////////////

// User record class declaration
class CAuthorsNoAttrAccessor
{
public:
   DWORD m_dwAuIDStatus;
   DWORD m_dwAuthorStatus;
   DWORD m_dwYearBornStatus;
   DWORD m_dwAuIDLength;
   DWORD m_dwAuthorLength;
   DWORD m_dwYearBornLength;
   LONG m_AuID;
   TCHAR m_Author[51];
   SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
   HRESULT OpenDataSource()
   {
      CDataSource _db;

HRESULT hr;
      hr = _db.OpenFromInitializationString(L"your connection string");
      if (FAILED(hr))
      {
#ifdef _DEBUG
         AtlTraceErrorRecords(hr);
#endif
         return hr;
      }
      return m_session.Open(_db);
   }
   void CloseDataSource()
   {
      m_session.Close();
   }
   operator const CSession&()
   {
      return m_session;
   }
   CSession m_session;
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)
   END_COLUMN_MAP()
};
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
{
public:
   HRESULT OpenAll()
   {
HRESULT hr;
      hr = OpenDataSource();
      if (FAILED(hr))
         return hr;
      __if_exists(GetRowsetProperties)
      {
         CDBPropSet propset(DBPROPSET_ROWSET);
         __if_exists(HasBookmark)
         {
            propset.AddProperty(DBPROP_IRowsetLocate, true);
         }
         GetRowsetProperties(&propset);
         return OpenRowset(&propset);
      }
      __if_not_exists(GetRowsetProperties)
      {
         __if_exists(HasBookmark)
         {
            CDBPropSet propset(DBPROPSET_ROWSET);
            propset.AddProperty(DBPROP_IRowsetLocate, true);
            return OpenRowset(&propset);
         }
      }
      return OpenRowset();
   }
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
   {
HRESULT hr = Open(m_session, "Authors", pPropSet);
#ifdef _DEBUG
      if(FAILED(hr))
         AtlTraceErrorRecords(hr);
#endif
      return hr;
   }
   void CloseAll()
   {
      Close();
      CloseDataSource();
   }
};
```

## <a name="see-also"></a>См. также

[Атрибуты объекта-получателя OLE DB](../../windows/ole-db-consumer-attributes.md)
