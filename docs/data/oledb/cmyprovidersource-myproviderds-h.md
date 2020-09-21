---
title: CCustomSource (CustomDS.H)
ms.date: 10/22/2018
f1_keywords:
- myproviderds.h
- cmyprovidersource
- customds.h
- ccustomsource
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
- CCustomSource class in CustomDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
ms.openlocfilehash: 8e92c30e8d62ade095167880917ad70da8e59b36
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742922"
---
# <a name="ccustomsource-customdsh"></a>Ккустомсаурце (Кустомдс. h)

Классы поставщиков используют множественное наследование. В следующем коде показана цепочка наследования для объекта источника данных.

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

Все COM-компоненты являются производными от `CComObjectRootEx` и `CComCoClass` . `CComObjectRootEx` предоставляет всю реализацию `IUnknown` интерфейса. Он может работать с любой потоковой моделью. `CComCoClass` обрабатывает все необходимые ошибки поддержки. Если вы хотите отправить клиенту более подробные сведения об ошибке, можно использовать некоторые API-интерфейсы ошибок в `CComCoClass` .

Объект источника данных также наследуется от нескольких классов "Impl". Каждый класс предоставляет реализацию для интерфейса. Объект источника данных реализует `IPersist` `IDBProperties` интерфейсы,, `IDBInitialize` и `IDBCreateSession` . Каждый интерфейс необходим OLE DB для реализации объекта источника данных. Можно выбрать поддержку или не поддерживать определенные функции, наследуя или не наследовать от одного из этих классов "Impl". Если требуется поддержка `IDBDataSourceAdmin` интерфейса, наследуйте `IDBDataSourceAdminImpl` класс, чтобы получить необходимые функциональные возможности.

## <a name="com-map"></a>Схема COM

Каждый раз, когда клиент вызывает `QueryInterface` интерфейс для источника данных, он проходит через следующую карту com:

```cpp
BEGIN_COM_MAP(CCustomSource)
   COM_INTERFACE_ENTRY(IDBCreateSession)
   COM_INTERFACE_ENTRY(IDBInitialize)
   COM_INTERFACE_ENTRY(IDBProperties)
   COM_INTERFACE_ENTRY(IPersist)
   COM_INTERFACE_ENTRY(IInternalConnection)
END_COM_MAP()
```

COM_INTERFACE_ENTRY макросы из библиотеки ATL и указывают реализации `QueryInterface` в `CComObjectRootEx` для возврата соответствующих интерфейсов.

## <a name="property-map"></a>Схема свойства

В сопоставлении свойств указаны все свойства, назначенные поставщиком:

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

Свойства в OLE DB группируются. Объект источника данных имеет две группы свойств: одно для набора DBPROPSET_DATASOURCEINFO и одно для набора DBPROPSET_DBINIT. Набор DBPROPSET_DATASOURCEINFO соответствует свойствам поставщика и его источника данных. Набор DBPROPSET_DBINIT соответствует свойствам, используемым при инициализации. Шаблоны поставщика OLE DB обрабатывали эти наборы с помощью макросов PROPERTY_SET. Макросы создают блок, содержащий массив свойств. Каждый раз, когда клиент вызывает `IDBProperties` интерфейс, поставщик использует карту свойств.

Не нужно реализовывать каждое свойство в спецификации. Однако необходимо поддерживать обязательные свойства. Дополнительные сведения см. в описании спецификации соответствия уровня 0. Если вы не хотите поддерживать свойство, его можно удалить из схемы. Если требуется поддержка свойства, добавьте его в карту с помощью макроса PROPERTY_INFO_ENTRY. Макрос соответствует `UPROPINFO` структуре, как показано в следующем коде:

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

Каждый элемент в структуре представляет сведения для управления этим свойством. Он содержит, `DBPROPID` чтобы определить идентификатор GUID и идентификатор для свойства. Он также содержит записи для определения типа и значения свойства.

Если необходимо изменить значение свойства по умолчанию (Обратите внимание, что потребитель может изменить значение свойства, доступного для записи в любое время), можно использовать макрос PROPERTY_INFO_ENTRY_VALUE или PROPERTY_INFO_ENTRY_EX. Эти макросы позволяют указать значение для соответствующего свойства. Макрос PROPERTY_INFO_ENTRY_VALUE — это сокращенная запись, позволяющая изменить значение. Макрос PROPERTY_INFO_ENTRY_VALUE вызывает макрос PROPERTY_INFO_ENTRY_EX. Этот макрос позволяет добавлять или изменять все атрибуты в `UPROPINFO` структуре.

Если вы хотите определить собственный набор свойств, его можно добавить, выполнив дополнительную комбинацию BEGIN_PROPSET_MAP и END_PROPSET_MAP. Определите идентификатор GUID для набора свойств, а затем определите собственные свойства. Если у вас есть свойства, зависящие от поставщика, добавьте их в новый набор свойств вместо использования существующего. Это позволяет избежать проблем в более поздних версиях OLE DB.

## <a name="user-defined-property-sets"></a>Определяемые пользователем наборы свойств

Visual C++ поддерживает наборы определяемых пользователем свойств. Нет необходимости переопределять `GetProperties` или `GetPropertyInfo` . Вместо этого шаблоны обнаруживают набор определяемых пользователем свойств и добавляют его к соответствующему объекту.

Если имеется набор свойств, определяемых пользователем, который должен быть доступен во время инициализации (то есть перед вызовом потребителя `IDBInitialize::Initialize` ), его можно указать с помощью флага UPROPSET_USERINIT вместе с макросом BEGIN_PROPERTY_SET_EX. Для этого набор свойств должен находиться в объекте источника данных (так как требуется спецификация OLE DB). Пример:

```cpp
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)
```

## <a name="see-also"></a>См. также

[Файлы, созданные мастером поставщика](../../data/oledb/provider-wizard-generated-files.md)<br/>
