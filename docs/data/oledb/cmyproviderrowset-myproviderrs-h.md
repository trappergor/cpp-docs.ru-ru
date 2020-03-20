---
title: CCustomRowset (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyproviderrowset
- ccustomrowset
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
ms.openlocfilehash: 2c84ff359bdbb39f281928fa0135edd40b1f7d20
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545807"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Мастер создает запись для объекта набора строк. В этом случае он называется `CCustomRowset`. Класс `CCustomRowset` наследует от класса поставщика OLE DB с именем `CRowsetImpl`, который реализует все необходимые интерфейсы для объекта набора строк. В следующем коде показана цепочка наследования для `CRowsetImpl`.

```cpp
template <class T, class Storage, class CreatorClass, 
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, 
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` также использует интерфейсы `IAccessor` и `IColumnsInfo`. Он использует эти интерфейсы для выходных полей в таблицах. Класс также предоставляет реализацию для `IRowsetIdentity`, которая позволяет потребителю определить, совпадают ли две строки. Интерфейс `IRowsetInfo` реализует свойства для объекта набора строк. Интерфейс `IConvertType` позволяет поставщику разрешать различия между типами данных, запрошенными потребителем, и теми, которые используются поставщиком.

Интерфейс `IRowset` фактически обрабатывает извлечение данных. Потребитель сначала вызывает метод, именуемый `GetNextRows`, чтобы вернуть маркер в строку, называемую `HROW`. Затем потребитель вызывает `IRowset::GetData` с этим `HROW` для получения запрошенных данных.

`CRowsetImpl` также принимает несколько параметров шаблона. Эти параметры позволяют определить, как класс `CRowsetImpl` обрабатывает данные. Аргумент `ArrayType` позволяет определить, какой механизм хранения используется для хранения данных строк. Параметр *ровкласс* указывает, какой класс содержит `HROW`.

Параметр *ровсетинтерфаце* позволяет также использовать интерфейс `IRowsetLocate` или `IRowsetScroll`. Интерфейсы `IRowsetLocate` и `IRowsetScroll` наследуются от `IRowset`. Таким образом, шаблоны поставщика OLE DB должны обеспечивать специальную обработку этих интерфейсов. Если вы хотите использовать любой из этих интерфейсов, необходимо использовать этот параметр.

## <a name="see-also"></a>См. также:

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)<br/>
