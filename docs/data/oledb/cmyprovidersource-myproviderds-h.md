---
title: "CMyProviderSource (MyProviderDS.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ""myproviderds.h""
  - "cmyprovidersource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSource - класс (MyProviderDS.H)"
  - "поставщики OLE DB, файлы, созданные мастером"
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSource (MyProviderDS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Классы поставщиков используют множественное наследование.  В следующем коде показана цепочка наследования для объекта источника данных:  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSource  
class ATL_NO_VTABLE CMyProviderSource :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public CComCoClass<CMyProviderSource, &CLSID_MyProvider>,  
   public IDBCreateSessionImpl<CMyProviderSource, CMyProviderSession>,  
   public IDBInitializeImpl<CMyProviderSource>,  
   public IDBPropertiesImpl<CMyProviderSource>,  
   public IPersistImpl<CMyProviderSource>,  
   public IInternalConnectionImpl<CMyProviderSource>  
```  
  
 Все компоненты COM наследуются от классов `CComObjectRootEx` и `CComCoClass`.  Класс `CComObjectRootEx` обеспечивает полную реализацию интерфейса **IUnknown**.  Он поддерживает обработку любой потоковой модели.  Класс `CComCoClass` поддерживает обработку любых ошибок.  При необходимости предоставления клиенту расширенных сведений об ошибках можно воспользоваться API\-интерфейсами обработки ошибок класса `CComCoClass`.  
  
 Объект источника данных также наследуется от некоторых классов с суффиксом "Impl".  Каждый класс обеспечивает реализацию интерфейса.  Объект источника данных реализует интерфейсы `IPersist`, `IDBProperties`, **IDBInitialize** и **IDBCreateSession**.  Каждый интерфейс необходим OLE DB для реализации объекта источника данных.  Выбрать поддержку конкретной функциональности можно путем наследования от одного из этих классов с суффиксом "Impl".  Для поддержки интерфейса **IDBDataSourceAdmin** необходимо обеспечить наследование от класса **IDBDataSourceAdminImpl**.  
  
## Сопоставление COM  
 Когда клиент вызывает метод `QueryInterface` для получения интерфейса источника данных, вызов выполняется в соответствии со следующим сопоставлением COM:  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 Макросы COM\_INTERFACE\_ENTRY, входящие в библиотеку ATL, указывают, какие интерфейсы должны возвращаться реализацией метода `QueryInterface` в классе `CComObjectRootEx`.  
  
## Сопоставление свойств  
 Сопоставление свойств определяет все свойства, заданные поставщиком:  
  
```  
BEGIN_PROPSET_MAP(CMyProviderSource)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)  
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)  
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)  
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)  
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)  
      PROPERTY_INFO_ENTRY(CATALOGTERM)  
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)  
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)  
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)  
      PROPERTY_INFO_ENTRY(DATASOURCENAME)  
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)  
      PROPERTY_INFO_ENTRY(DBMSNAME)  
      PROPERTY_INFO_ENTRY(DBMSVER)  
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)  
      PROPERTY_INFO_ENTRY(GROUPBY)  
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)  
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)  
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)  
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)  
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)  
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)  
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)  
      PROPERTY_INFO_ENTRY(NULLCOLLATION)  
      PROPERTY_INFO_ENTRY(OLEOBJECTS)  
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)  
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)  
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)  
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PROCEDURETERM)  
      PROPERTY_INFO_ENTRY(PROVIDERNAME)  
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)  
      PROPERTY_INFO_ENTRY(PROVIDERVER)  
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)  
      PROPERTY_INFO_ENTRY(SCHEMATERM)  
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)  
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)  
      PROPERTY_INFO_ENTRY(SUBQUERIES)  
      PROPERTY_INFO_ENTRY(TABLETERM)  
      PROPERTY_INFO_ENTRY(USERNAME)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)  
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)  
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)  
      PROPERTY_INFO_ENTRY(AUTH_USERID)  
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)  
      PROPERTY_INFO_ENTRY(INIT_HWND)  
      PROPERTY_INFO_ENTRY(INIT_LCID)  
      PROPERTY_INFO_ENTRY(INIT_LOCATION)  
      PROPERTY_INFO_ENTRY(INIT_MODE)  
      PROPERTY_INFO_ENTRY(INIT_PROMPT)  
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)  
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)  
   END_PROPERTY_SET(DBPROPSET_DBINIT)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)  
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)  
   CHAIN_PROPERTY_SET(CMyProviderSession)  
END_PROPSET_MAP()  
```  
  
 Свойства OLE DB группируются.  Объект источника данных имеет две группы свойств: одна для набора **DBPROPSET\_DATASOURCEINFO** и одна для набора **DBPROPSET\_DBINIT**.  Набор **DBPROPSET\_DATASOURCEINFO** соответствует свойствам, относящимся к поставщику и его источнику данных.  Набор **DBPROPSET\_DBINIT** соответствует свойствам, используемым при инициализации.  Шаблоны поставщика OLE DB обрабатывают эти наборы с помощью макросов PROPERTY\_SET.  Макросы создают блок, содержащий массив свойств.  При вызове клиентом интерфейса `IDBProperties` поставщик использует сопоставление свойств.  
  
 Нет необходимости реализовывать каждое свойство, описанное в спецификации.  Однако должны поддерживаться необходимые свойства. Дополнительные сведения см. в спецификации соответствия базового уровня.  Если поддержка данного свойства не нужна, его можно удалить из сопоставления.  Если требуется поддержка какого\-либо свойства, его следует добавить в сопоставление с помощью макроса PROPERTY\_INFO\_ENTRY.  Макрос соответствует структуре **UPROPINFO**, как показано в следующем коде:  
  
```  
struct UPROPINFO  
{  
   DBPROPID    dwPropId;  
   ULONG       ulIDS;  
   VARTYPE     VarType;  
   DBPROPFLAGS dwFlags;  
   union  
   {  
      DWORD dwVal;  
      LPOLESTR szVal;  
   };  
   DBPROPOPTIONS dwOption;  
};  
```  
  
 Каждый элемент структуры представляет данные для обработки свойства.  В нем содержится идентификатор **DBPROPID**, используемый для определения GUID и идентификатора свойства.  В нем также содержатся записи, используемые для определения типа и значения свойства.  
  
 Если необходимо изменить значение свойства по умолчанию \(обратите внимание, что объект\-получатель может изменить значение свойства, доступного для записи, в любое время\), можно воспользоваться макросами PROPERTY\_INFO\_ENTRY\_VALUE или PROPERTY\_INFO\_ENTRY\_EX.  Эти макросы позволяют указывать значение для соответствующего свойства.  Макрос PROPERTY\_INFO\_ENTRY\_VALUE — это сокращенная запись, позволяющая изменять значения.  Макрос PROPERTY\_INFO\_ENTRY\_VALUE вызывает макрос PROPERTY\_INFO\_ENTRY\_EX.  Этот макрос позволяет добавлять или изменять любые атрибуты структуры **UPROPINFO**.  
  
 Если необходимо определить собственный набор свойств, его можно добавить, создав дополнительное сочетание BEGIN\_PROPSET\_MAP\/END\_PROPSET\_MAP.  Следует сперва определить GUID для набора свойств, а затем определять собственные свойства.  При наличии свойств, связанных с поставщиком, их следует добавить в новый набор свойств, а не в уже существующий.  Это позволяет избежать проблем в последних версиях OLE DB.  
  
## Пользовательские наборы свойств  
 Visual C\+\+ .NET поддерживает пользовательские наборы свойств.  Теперь нет необходимости переопределять методы **GetProperties** или `GetPropertyInfo`.  Вместо этого шаблоны обнаруживают наличие пользовательских наборов свойств и добавляют их в соответствующие объекты.  
  
 Если пользовательский набор свойств должен быть доступен на этапе инициализации \(т. е. до того как объект\-получатель вызовет метод **IDBInitialize::Initialize**\), следует использовать флаг **UPROPSET\_USERINIT** в сочетании с макросом BEGIN\_PROPERTY\_SET\_EX.  Для правильной работы набор свойств должен находиться в объекте источника данных \(в соответствии с требованиями спецификации OLE DB\).  Примеры.  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)