---
title: CCustomSource (CustomDS.H) | Документация Майкрософт
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- myproviderds.h
- cmyprovidersource
- customds.h
- ccustomsource
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
- CCustomSource class in CustomDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bcabecde8f299e878ec6498dada503a894c406b4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081135"
---
# <a name="ccustomsource-customdsh"></a>CCustomSource (CustomDS.h)

Классы поставщиков используют множественное наследование. Следующий код показывает цепочку наследования для объекта источника данных:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource :
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

Все COM-компоненты являются производными от `CComObjectRootEx` и `CComCoClass`. `CComObjectRootEx` предоставляет реализацию для `IUnknown` интерфейс. Он может обрабатывать любой потоковой модели. `CComCoClass` обрабатывает любые ошибки поддержку, что необходимо. Если вы хотите отправлять клиенту сведений об ошибках, можно использовать некоторые ошибки API-интерфейсы в `CComCoClass`.

Объект источника данных также наследует из нескольких классов с суффиксом «Impl». Каждый класс предоставляет реализацию для интерфейса. Источник данных реализует объект `IPersist`, `IDBProperties`, `IDBInitialize`, и `IDBCreateSession` интерфейсов. Каждый интерфейс OLE DB необходима для реализации объекта источника данных. Вы можете поддерживать или не поддерживает конкретную функцию путем наследования от одного из этих классов с суффиксом «Impl». Если вы хотите поддерживать `IDBDataSourceAdmin` интерфейс, можно наследовать от `IDBDataSourceAdminImpl` класса, чтобы получить функциональность, необходимую.

## <a name="com-map"></a>Сопоставления COM

Каждый раз, когда клиент вызывает `QueryInterface` для получения интерфейса источника данных, он проходит через следующие сопоставления COM:

```cpp
BEGIN_COM_MAP(CCustomSource)
   COM_INTERFACE_ENTRY(IDBCreateSession)
   COM_INTERFACE_ENTRY(IDBInitialize)
   COM_INTERFACE_ENTRY(IDBProperties)
   COM_INTERFACE_ENTRY(IPersist)
   COM_INTERFACE_ENTRY(IInternalConnection)
END_COM_MAP()
```

Макросы COM_INTERFACE_ENTRY из ATL и сообщить реализация `QueryInterface` в `CComObjectRootEx` для возврата соответствующие интерфейсы.

## <a name="property-map"></a>Сопоставление свойств

Сопоставление свойств определяет все свойства, заданное поставщиком:

```cpp
BEGIN_PROPSET_MAP(CCustomSource)
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
   CHAIN_PROPERTY_SET(CCustomSession)
END_PROPSET_MAP()
```

Свойства OLE DB группируются. Объект источника данных есть две группы свойств: один для DBPROPSET_DATASOURCEINFO задать и один для DBPROPSET_DBINIT значение. Набор DBPROPSET_DATASOURCEINFO соответствует свойства поставщика и источника данных. Набор DBPROPSET_DBINIT соответствует свойствам, используемым при инициализации. Шаблоны поставщика OLE DB обрабатывают эти наборы с помощью макросов PROPERTY_SET. Макросы создают блок, содержащий массив свойств. Каждый раз, когда клиент вызывает `IDBProperties` интерфейс, поставщик использует сопоставление свойств.

Необходимо реализовать каждое свойство в спецификации. Тем не менее необходимо поддерживать необходимые свойства. см. в уровень 0 соответствия спецификации Дополнительные сведения. Если вы не хотите поддерживает свойство, можно удалить его из сопоставления. Если требуется поддерживать свойство, добавьте его в карту с помощью PROPERTY_INFO_ENTRY-макрос. Макрос соответствует `UPROPINFO` структуры, как показано в следующем коде:

```cpp
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

Каждый элемент структуры представляет сведения для обработки свойства. Он содержит `DBPROPID` для определения GUID и идентификатора свойства. Он также содержит записи, чтобы определить тип и значение свойства.

Если вы хотите изменить значение по умолчанию свойства (Обратите внимание, что объект-получатель можно изменить значение свойства для записи в любое время), можно использовать макрос PROPERTY_INFO_ENTRY_VALUE или PROPERTY_INFO_ENTRY_EX. Эти макросы позволяют пользователю указать значение для соответствующего свойства. PROPERTY_INFO_ENTRY_VALUE-макрос является сокращенной записи, которая позволяет изменить значение. PROPERTY_INFO_ENTRY_VALUE-макрос вызывает PROPERTY_INFO_ENTRY_EX-макрос. Этот макрос позволяет добавлять или изменять все атрибуты в `UPROPINFO` структуры.

Если вы хотите определить собственный набор свойств, можно добавить, создав дополнительные сочетание BEGIN_PROPSET_MAP/END_PROPSET_MAP. Необходимо определить GUID для набора свойств, а затем определите собственные свойства. При наличии свойства поставщика, их необходимо добавьте в новый набор свойств, вместо того чтобы использовать уже существующий. Это позволяет избежать проблем в более поздних версиях OLE DB.

## <a name="user-defined-property-sets"></a>Наборы пользовательских свойств

Visual C++ поддерживает наборы пользовательских свойств. У вас нет в Переопределите `GetProperties` или `GetPropertyInfo`. Вместо этого шаблоны обнаружения любой набор определяемых пользователем свойств и добавить его в соответствующий объект.

Если у вас есть набор определяемых пользователем свойств, который должен быть доступным во время инициализации (то есть, прежде чем потребитель вызывает метод `IDBInitialize::Initialize`), это можно указать с помощью флага UPROPSET_USERINIT в сочетании с begin_property_set_ex-макрос. Набор свойств должны находиться в объекте источника данных для правильной работы (как требуется спецификацией OLE DB). Пример:

```cpp
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)
```

## <a name="see-also"></a>См. также

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)