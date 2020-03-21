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
ms.openlocfilehash: 8e90db287bc7ac8994914766045eb210446dfd48
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079784"
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
