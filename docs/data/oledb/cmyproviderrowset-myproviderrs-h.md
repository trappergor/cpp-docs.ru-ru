---
title: CMyProviderRowset (MyProviderRS.H) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7bfd7c927342790fee3be2b5a7d48bccba3ea168
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmyproviderrowset-myproviderrsh"></a>CMyProviderRowset (MyProviderRS.H)
Мастер создает запись для объекта набора строк. В данном случае файл называется `CMyProviderRowset`. `CMyProviderRowset` Класс наследует класс поставщика OLE DB с именем `CRowsetImpl`, который реализует интерфейсы, необходимые для объекта набора строк. В следующем коде показано цепочку наследования для `CRowsetImpl`:  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T >>  
```  
  
 `CRowsetImpl` также использует `IAccessor` и `IColumnsInfo` интерфейсов. Она использует эти интерфейсы для выводов полей в таблицах. Класс также предоставляет реализацию для **IRowsetIdentity**, который позволяет потребителю для определения идентичности двух строк. `IRowsetInfo` Интерфейс реализует свойства для объекта набора строк. **IConvertType** интерфейс позволяет устранить различия между типами данных, запрошенными объектом-получателем и используемых поставщиком поставщику.  
  
 `IRowset` Интерфейс фактически обрабатывает извлечения данных. Потребитель сначала вызывает метод с именем `GetNextRows` возвращает дескриптор строки, известный как **HROW**. Затем потребитель вызывает метод **IRowset::GetData** , **HROW** для получения запрошенных данных.  
  
 `CRowsetImpl` также принимает несколько параметров шаблонов. Эти параметры позволяют определить, каким образом `CRowsetImpl` класс обрабатывает данные. `ArrayType` Аргумент позволяет определить механизм хранения, используемый для хранения данных строки. **RowClass** параметр указывает, какой класс содержит **HROW**.  
  
 **RowsetInterface** позволяет также использовать `IRowsetLocate` или `IRowsetScroll` интерфейса. `IRowsetLocate` И `IRowsetScroll` интерфейсы являются производными от `IRowset`. Таким образом шаблоны поставщика OLE DB должны предоставлять особую обработку для этих интерфейсов. Если вы хотите использовать один из этих интерфейсов, необходимо использовать этот параметр.  
  
## <a name="see-also"></a>См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)