---
title: CCustomRowset (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
- ccustomrowset
- customrs.h
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
ms.openlocfilehash: 2e54b1f3434434dc8c6028bc04a8b1dba17d8305
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434973"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Мастер формирует запись для объекта набора строк. В этом случае он называется `CCustomRowset`. `CCustomRowset` Класс наследует от класса поставщика OLE DB вызывается `CRowsetImpl`, который реализует все интерфейсы, необходимые для объекта набора строк. Следующий код показывает цепочку наследования для `CRowsetImpl`:

```cpp
template <class T, class Storage, class CreatorClass, 
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, 
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` также использует `IAccessor` и `IColumnsInfo` интерфейсов. Она использует эти интерфейсы для поля выходных данных в таблицах. Класс также предоставляет реализацию для `IRowsetIdentity`, что позволяет потребителю определить, совпадают ли две строки. `IRowsetInfo` Интерфейс реализует свойства для объекта набора строк. `IConvertType` Интерфейс позволяет поставщику урегулировать различия между типами данных, запрошенный объектом-получателем и тех, которые используются поставщиком.

`IRowset` Интерфейс фактически обрабатывает получение данных. Во-первых, потребитель вызывает метод, вызванный `GetNextRows` возвращает дескриптор строки, известный как `HROW`. Затем потребитель вызывает метод `IRowset::GetData` с, `HROW` для получения запрошенных данных.

`CRowsetImpl` также принимает несколько параметров шаблона. Эти параметры позволяют определить, каким образом `CRowsetImpl` класс обрабатывает данные. `ArrayType` Аргумент позволяет определить, какой механизм хранения используется для хранения данных в строке. *RowClass* параметр указывает, какой класс содержит `HROW`.

*RowsetInterface* параметр можно также использовать `IRowsetLocate` или `IRowsetScroll` интерфейс. `IRowsetLocate` И `IRowsetScroll` интерфейсы являются производными от `IRowset`. Таким образом шаблоны поставщика OLE DB необходимо указать специальную обработку для этих интерфейсов. Если вы хотите использовать один из этих интерфейсов, необходимо использовать этот параметр.

## <a name="see-also"></a>См. также

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)<br/>
