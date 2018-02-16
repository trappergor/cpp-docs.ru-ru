---
title: "CMyProviderSource (MyProviderDS.H) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- myproviderds.h
- cmyprovidersource
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8704a4a0733ea8bf688378953af9ff01314271d1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cmyprovidersource-myproviderdsh"></a>CMyProviderSource (MyProviderDS.H)
Классы поставщиков используют множественное наследование. В следующем коде показано цепочку наследования для объекта источника данных:  
  
```cpp
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
  
 Все компоненты COM являются производными от `CComObjectRootEx` и `CComCoClass`. `CComObjectRootEx` предоставляет реализацию для **IUnknown** интерфейса. Он может обрабатывать любой потоковой модели. `CComCoClass` обрабатывает необходима поддержка любые ошибки. Если вы хотите отправить клиенту сведений об ошибках, можно использовать некоторые ошибки API-интерфейсы в `CComCoClass`.  
  
 Объект источника данных также наследуется от нескольких классов суффиксом «Impl». Каждый класс предоставляет реализацию для интерфейса. Источник данных реализует объект `IPersist`, `IDBProperties`, **IDBInitialize**, и **IDBCreateSession** интерфейсов. Каждый интерфейс необходим OLE DB для реализации объекта источника данных. Вы можете поддерживать или не поддерживать конкретной функции путем наследования от одного из этих классов с суффиксом «Impl». Если вы хотите поддерживать **IDBDataSourceAdmin** интерфейс, наследовать от **IDBDataSourceAdminImpl** класса, чтобы получить функциональность, необходимую.  
  
## <a name="com-map"></a>Сопоставление COM  
 Каждый раз, когда клиент вызывает `QueryInterface` для получения интерфейса источника данных, выполняется в соответствии со следующим сопоставлением COM:  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 Макросы COM_INTERFACE_ENTRY из ATL и сообщите реализация `QueryInterface` в `CComObjectRootEx` для возврата соответствующие интерфейсы.  
  
## <a name="property-map"></a>Сопоставление свойств  
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
  
 Свойства OLE DB группируются. Объект источника данных есть две группы свойств: одно для **DBPROPSET_DATASOURCEINFO** и одну для **DBPROPSET_DBINIT** значение. **DBPROPSET_DATASOURCEINFO** набор соответствует свойствам о поставщике и источником данных. **DBPROPSET_DBINIT** набор соответствует свойствам, используемым при инициализации. Шаблоны поставщика OLE DB обрабатывают эти наборы с помощью макросов PROPERTY_SET. Макросы создают блок, содержащий массив свойств. Каждый раз, когда клиент вызывает `IDBProperties` интерфейс, поставщик использует сопоставление свойств.  
  
 Необходимо реализовать все свойства в соответствии со спецификацией. Тем не менее необходимо поддерживать необходимые свойства. см. спецификацию соответствия уровня 0 для получения дополнительной информации. Если вы не хотите поддерживает свойство, можно удалить его из сопоставления. Если вы хотите поддерживает свойство, добавьте его в сопоставление с помощью PROPERTY_INFO_ENTRY-макрос. Макрос соответствует **UPROPINFO** структуры, как показано в следующем коде:  
  
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
  
 Каждый элемент структуры представляет данные для обработки свойства. Он содержит **DBPROPID** для определения GUID и идентификатора свойства. Он также содержит записи, чтобы определить тип и значение свойства.  
  
 Если вы хотите изменить значение по умолчанию свойства (Обратите внимание, что объект-получатель можно изменить значение для записи свойства в любое время), можно использовать макрос PROPERTY_INFO_ENTRY_VALUE или PROPERTY_INFO_ENTRY_EX. Эти макросы позволяют указать значение для соответствующего свойства. PROPERTY_INFO_ENTRY_VALUE-макрос является сокращенной записи, которая позволяет изменить значение. PROPERTY_INFO_ENTRY_VALUE-макрос вызывает PROPERTY_INFO_ENTRY_EX-макрос. Этот макрос позволяет добавлять или изменять любые атрибуты в **UPROPINFO** структуры.  
  
 Если вы хотите определить собственный набор свойств, можно добавить, создав дополнительные сочетание BEGIN_PROPSET_MAP/END_PROPSET_MAP. Необходимо определить GUID для набора свойств, а затем определять собственные свойства. При наличии свойства поставщика, добавьте их в новый набор, вместо того чтобы использовать один из существующих свойств. Это позволяет избежать проблем в более поздних версиях OLE DB.  
  
## <a name="user-defined-property-sets"></a>Задает определяемые пользователем  
 Visual C++ поддерживает наборы пользовательских свойств. Необходимо переопределить **GetProperties** или `GetPropertyInfo`. Вместо этого шаблоны обнаружения любой набор определяемых пользователем свойств и добавить его к соответствующему объекту.  
  
 Если у вас есть набор пользовательских свойств, которые должны быть доступны во время инициализации (то есть до потребитель вызывает метод **IDBInitialize::Initialize**), это можно указать с помощью **UPROPSET_USERINIT** флаг в сочетании с begin_property_set_ex-макрос. Набор свойств должен находиться в объекте источника данных для правильной работы (как требуется спецификацией OLE DB). Пример:  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## <a name="see-also"></a>См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)