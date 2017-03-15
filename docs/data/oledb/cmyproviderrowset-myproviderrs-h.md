---
title: "CMyProviderRowset (MyProviderRS.H) | Microsoft Docs"
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
  - "cmyproviderrowset"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderRowset - класс (MyProviderRS.H)"
  - "поставщики OLE DB, файлы, созданные мастером"
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderRowset (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Мастер создает запись для объекте набора строк.  В этом случае запись называется `CMyProviderRowset`.  Класс `CMyProviderRowset` является производным от класса `CRowsetImpl` поставщика OLE DB, который реализует все необходимые интерфейсы для объекта набора записей.  В следующем примере кода демонстрируется цепь наследования для `CRowsetImpl`:  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T > >  
```  
  
 Класс `CRowsetImpl` также использует интерфейсы `IAccessor` и `IColumnsInfo`.  Он использует указанные интерфейсы для выводов полей в таблицах.  Класс также предоставляет реализацию для интерфейса **IRowsetIdentity**, позволяющего объекту\-получателю определять, являются ли идентичными два набора записей.  Интерфейс `IRowsetInfo` реализует свойства для объекта набора записей.  Интерфейс **IConvertType** позволяет поставщику урегулировать различия между типами данных, запрошенными объектом\-получателем, и типами данных, используемыми поставщиком.  
  
 Интерфейс `IRowset` осуществляет обработку извлекаемых данных.  Объект\-получатель, в первую очередь, использует метод `GetNextRows` и возвращает дескриптор строки, известный как **HROW**.  Затем объект вызывает **IRowset::GetData** вместе с **HROW**, чтобы получить необходимые данные.  
  
 `CRowsetImpl` также принимает несколько параметров шаблонов.  Эти параметры позволяют определить метод обработки данных классом `CRowsetImpl`.  Аргумент `ArrayType` позволяет определить механизм хранения, используемый для хранения данных строки.  Параметр **RowClass** указывает на класс, который содержит **HROW**.  
  
 Параметр **RowsetInterface** позволяет использовать интерфейс `IRowsetLocate` или `IRowsetScroll`.  Интерфейсы `IRowsetLocate` и `IRowsetScroll` являются производными от `IRowset`.  Таким образом, шаблоны поставщиков OLE DB должны предоставлять особую обработку для этих интерфейсов.  Если необходимо использовать указанные выше интерфейсы, используйте этот параметр.  
  
## См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)