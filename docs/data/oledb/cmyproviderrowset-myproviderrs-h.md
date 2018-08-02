---
title: CMyProviderRowset (MyProviderRS.H) | Документация Майкрософт
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
ms.openlocfilehash: 936c8fe849e2eb92b8eb46170fc3e67842ad6beb
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338854"
---
# <a name="cmyproviderrowset-myproviderrsh"></a>CMyProviderRowset (MyProviderRS.H)
Мастер формирует запись для объекта набора строк. В данном случае файл называется `CMyProviderRowset`. `CMyProviderRowset` Класс наследует от класса поставщика OLE DB вызывается `CRowsetImpl`, который реализует все интерфейсы, необходимые для объекта набора строк. Следующий код показывает цепочку наследования для `CRowsetImpl`:  
  
```cpp  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T >>  
```  
  
 `CRowsetImpl` также использует `IAccessor` и `IColumnsInfo` интерфейсов. Она использует эти интерфейсы для поля выходных данных в таблицах. Класс также предоставляет реализацию для `IRowsetIdentity`, что позволяет потребителю определить, если две строки идентичны. `IRowsetInfo` Интерфейс реализует свойства для объекта набора строк. `IConvertType` Интерфейс позволяет поставщику урегулировать различия между типами данных, запрошенный объектом-получателем и тех, которые используются поставщиком.  
  
 `IRowset` Интерфейс фактически обрабатывает получение данных. Во-первых, потребитель вызывает метод, вызванный `GetNextRows` возвращает дескриптор строки, известный как `HROW`. Затем потребитель вызывает метод `IRowset::GetData` с, `HROW` для получения запрошенных данных.  
  
 `CRowsetImpl` также принимает несколько параметров шаблона. Эти параметры позволяют определить, каким образом `CRowsetImpl` класс обрабатывает данные. `ArrayType` Аргумент позволяет определить, какой механизм хранения используется для хранения данных в строке. *RowClass* параметр указывает, какой класс содержит `HROW`.  
  
 *RowsetInterface* параметр можно также использовать `IRowsetLocate` или `IRowsetScroll` интерфейс. `IRowsetLocate` И `IRowsetScroll` интерфейсы являются производными от `IRowset`. Таким образом шаблоны поставщика OLE DB необходимо указать специальную обработку для этих интерфейсов. Если вы хотите использовать один из этих интерфейсов, необходимо использовать этот параметр.  
  
## <a name="see-also"></a>См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)