---
title: Доступ к данным XML
ms.date: 10/18/2018
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
ms.openlocfilehash: be4225003211449a98d3fbe5fd686b9b8058a651
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212281"
---
# <a name="accessing-xml-data"></a>Доступ к данным XML

Существует два отдельных метода получения XML-данных из источника данных: один использует [CStreamRowset](../../data/oledb/cstreamrowset-class.md) , а другой использует [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).

|Функциональность|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|Объем передаваемых данных|Извлекает данные из всех столбцов и строк за один раз.|Извлекает данные из всех столбцов, но только по одной строке за раз. Необходимо перемещаться по строкам с помощью таких методов, как `MoveNext`.|
|Форматирование строки|SQL Server форматирует XML-строку и отправляет ее потребителю.|Извлекает данные набора строк в собственном формате (запрос, который поставщик отправляет в виде строк в Юникоде), а затем создает строку, содержащую данные в формате XML.|
|Управление форматированием|Существует определенный уровень контроля над форматированием XML-строки путем установки некоторых свойств SQL Server 2000.|Вы не контролируете формат созданной XML-строки.|

Хотя `CStreamRowset` предоставляет более общий эффективный способ извлечения данных в формате XML, он поддерживается только SQL Server 2000.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>Получение XML-данных с помощью CStreamRowset

Укажите [CStreamRowset](../../data/oledb/cstreamrowset-class.md) в качестве типа набора строк в объявлении `CCommand` или `CTable`. Его можно использовать с собственным методом доступа или без него, например:

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

-или-

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

Обычно при вызове `CCommand::Open` (например, `CRowset` как класс `TRowset`) он получает указатель `IRowset`. `ICommand::Execute` возвращает указатель `IRowset`, который хранится в `m_spRowset` элементе `CRowset` объекта. Такие методы, как `MoveFirst`, `MoveNext`и `GetData`, используют этот указатель для получения данных.

Напротив, при вызове `CCommand::Open` (но указание `CStreamRowset` в качестве `TRowset` класса) `ICommand::Execute` возвращает указатель `ISequentialStream`, который хранится в элементе данных `m_spStream` [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Затем используется метод `Read` для получения данных (строки в Юникоде) в формате XML. Пример:

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000 выполняет форматирование XML и возвращает все столбцы и все строки набора строк в виде одной строки XML.

Пример использования метода `Read` см. в разделе **Добавление поддержки XML к потребителю** при [реализации простого потребителя](../../data/oledb/implementing-a-simple-consumer.md).

> [!NOTE]
> Поддержка XML с использованием `CStreamRowset` работает только с SQL Server 2000 и требует наличия поставщика OLE DB для SQL Server 2000 (устанавливается вместе с MDAC).

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>Получение XML-данных с помощью CXMLAccessor

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) позволяет получать доступ к данным из источника данных в виде строковых данных, если нет сведений о схеме хранилища данных. `CXMLAccessor` работает так же, как `CDynamicStringAccessorW`, за исключением того, что первый преобразует все данные, доступ к которым осуществлялся из хранилища данных, в формате XML (с тегами). Имена XML-тегов совпадают с именами столбцов хранилища данных как можно точнее.

Используйте `CXMLAccessor`, как и любой другой класс метода доступа, передав его в качестве параметра шаблона в `CCommand` или `CTable`:

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

Используйте [жетксмлровдата](../../data/oledb/cxmlaccessor-getxmlrowdata.md) для получения данных из таблицы по одной строке за раз и перехода по строкам с помощью таких методов, как `MoveNext`, например:

```cpp
// Open data source, session, and rowset
hr = rs.MoveFirst();

while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
{
    CStringW strRowData;
    myCmd.GetXMLRowData(strRowData);

    printf_s( "%S\n", strRowData );

    hr = rs.MoveNext();
}
```

[Жетксмлколумндата](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) можно использовать для получения сведений о столбце (типе данных) в виде строковых данных в формате XML.

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)
