---
title: "Изменение порядка наследования класса RMyProviderRowset | Microsoft Docs"
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
  - "наследование [C++]"
  - "RMyProviderRowset"
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Изменение порядка наследования класса RMyProviderRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтобы добавить интерфейс `IRowsetLocate` к примеру простого поставщика, предназначенного только для чтения, измените порядок наследования класса **RMyProviderRowset**.  Изначально класс **RMyProviderRowset** наследуется от класса `CRowsetImpl`.  В этом случае необходимо определить его наследование от класса **CRowsetBaseImpl**.  
  
 Для этого создайте в файле MyProviderRS.h новый класс `CMyRowsetImpl`:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate > >  
{  
...  
};  
```  
  
 В файле MyProviderRS.h измените схему интерфейса COM следующим образом:  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 При этом создается схема интерфейса COM, в которой определяется вызов в классе `CMyRowsetImpl` метода **QueryInterface** одновременно для интерфейсов `IRowset` и `IRowsetLocate`.  Чтобы получить все реализации других классов набора строк, класс `CMyRowsetImpl` повторно связывается в схеме с классом **CRowsetBaseImpl**, определенным в шаблонах OLE DB. В схеме используется макрос COM\_INTERFACE\_ENTRY\_CHAIN, в котором определяется поиск с помощью шаблонов OLE DB в схеме COM класса **CRowsetBaseImpl** при вызове метода `QueryInterface`.  
  
 Свяжите класс `RAgentRowset` с классом `CMyRowsetBaseImpl`. Для этого определите наследование класса `RAgentRowset` от `CMyRowsetImpl`, как показано ниже:  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 После этого в классе `RAgentRowset` можно использовать интерфейс `IRowsetLocate`, а также возможности остальных реализаций класса набора строк.  
  
 По завершении можно выполнить [динамическое определение столбцов, возвращаемых в объект\-получатель](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## См. также  
 [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)