---
title: "Упрощение доступа к данным с помощью атрибутов базы данных | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "атрибуты [C++], доступ к данным"
  - "атрибуты [C++], база данных"
  - "атрибуты [C++], потребитель OLE DB"
  - "данные [C++], упрощение доступа"
  - "доступ к данным [C++], атрибуты баз данных"
  - "атрибуты баз данных [C++]"
  - "базы данных [C++], атрибуты"
  - "потребители OLE DB [C++], атрибуты баз данных"
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Упрощение доступа к данным с помощью атрибутов базы данных
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В разделе демонстрируется использование атрибутов базы данных, которые упрощают выполнение операций.  
  
 Основной способ подключения к информации из базы данных — это создание класса \(или таблицы\) команды и пользовательского класса записей для конкретной таблицы в базе данных.  Атрибуты базы данных упрощают создание некоторых объявлений шаблонов, которые приходилось делать ранее.  
  
 Для того чтобы продемонстрировать использование атрибутов базы данных, в следующих разделах показаны две аналогичных таблицы и объявление пользовательского класса записей: в первой таблице используются атрибуты, а во второй — шаблоны OLE DB.  Подобный код объявления обычно размещают в файле заголовка под названием для таблицы или объекта команды, например Authors.h.  
  
 Сравнивая два файла, можно увидеть, насколько упростилась работа с атрибутами.  Ниже указаны следующие различия:  
  
-   Применяя атрибуты, следует объявлять один класс `CAuthors`, а при работе с шаблонами — два класса: `CAuthorsNoAttrAccessor` и `CAuthorsNoAttr`.  
  
-   Вызов `db_source` в версии с атрибутами приравнивается к вызову`OpenDataSource()` в объявлении шаблона.  
  
-   Вызов **db\_table** в версии с атрибутами приравнивается к нижеуказанном объявлении шаблона:  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
    ```  
  
-   Вызовы **db\_column** в версии с атрибутами приравниваются к сопоставлению столбцов в объявлении шаблона \(см. в разделе `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`\).  
  
 Атрибуты встраивают пользовательский класс записи.  Пользовательский класс записи приравнивается к `CAuthorsNoAttrAccessor` в объявлении шаблона.  Если класс таблицы представлен как `CAuthors`, а встроенный пользовательский класс записи обозначен как `CAuthorsAccessor`, объявление во встроенном коде будет доступно только для просмотра.  Дополнительные сведения см.в подразделе "Встроенные атрибуты в пользовательском классе записи" в разделе [Пользовательские записи](../../data/oledb/user-records.md).  
  
 Обратите внимание, что в атрибутах и коде с шаблонами необходимо настроить свойства набора строк с помощью `CDBPropSet::AddProperty`.  
  
 Дополнительные сведения об атрибутах, рассмотренных в данном подразделе, см. в разделе [Атрибуты объекта\-получателя OLE DB](../../windows/ole-db-consumer-attributes.md).  
  
## Таблицы и объявление метода доступа с помощью атрибутов  
 Следующий код вызывает `db_source` и **db\_table** класса таблицы.  `db_source` задает источник данных и подключение, которое следует использовать.  **db\_table** встраивает соответствующий код шаблона для объявления класса таблицы.  **db\_column** определяет сопоставление столбцов и встраивает объявление метода доступа.  Атрибуты объекта\-получателя OLE DB используются в любом проекте, который поддерживает ATL.  
  
 Ниже указаны таблицы и объявление методов доступа с помощью атрибутов  
  
```  
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
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
};  
```  
  
## Таблицы и объявление метода доступа с помощью атрибутов  
 Ниже указаны таблицы и объявление метода доступа с помощью шаблонов.  
  
```  
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
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
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
  
## См. также  
 [OLE DB Consumer Attributes](../../windows/ole-db-consumer-attributes.md)   
 [Attributes Walkthroughs](http://msdn.microsoft.com/ru-ru/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)