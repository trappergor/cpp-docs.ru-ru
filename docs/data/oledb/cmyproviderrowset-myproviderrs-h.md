---
title: CCustomRowset (CustomRS.H) | Документация Майкрософт
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
- ccustomrowset
- customrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4808f9165fa6f139b0d3b576620e9db80eb360d3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077001"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Мастер формирует запись для объекта набора строк. В данном случае файл называется `CCustomRowset`. `CCustomRowset` Класс наследует от класса поставщика OLE DB вызывается `CRowsetImpl`, который реализует все интерфейсы, необходимые для объекта набора строк. Следующий код показывает цепочку наследования для `CRowsetImpl`:

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