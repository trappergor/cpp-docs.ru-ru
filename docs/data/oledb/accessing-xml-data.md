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
ms.openlocfilehash: 437f1d103420ec5727294894c02587c68cffbdda
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509132"
---
# <a name="accessing-xml-data"></a>Доступ к данным XML

Существует два отдельных метода получения XML-данных из источника данных: один использует [CStreamRowset](../../data/oledb/cstreamrowset-class.md) , а другой использует [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).

|Функциональность|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|Объем передаваемых данных|Извлекает данные из всех столбцов и строк за один раз.|Извлекает данные из всех столбцов, но только по одной строке за раз. Необходимо перемещаться по строкам с помощью таких методов, как `MoveNext` .|
|Форматирование строки|SQL Server форматирует XML-строку и отправляет ее потребителю.|Извлекает данные набора строк в собственном формате (запрос, который поставщик отправляет в виде строк в Юникоде), а затем создает строку, содержащую данные в формате XML.|
|Управление форматированием|Существует определенный уровень контроля над форматированием XML-строки путем установки некоторых свойств SQL Server 2000.|Вы не контролируете формат созданной XML-строки.|

Хотя `CStreamRowset` предоставляет более эффективный способ получения данных в формате XML, он поддерживается только SQL Server 2000.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>Получение XML-данных с помощью CStreamRowset

Укажите [CStreamRowset](../../data/oledb/cstreamrowset-class.md) в качестве типа набора строк в `CCommand` `CTable` объявлении или. Его можно использовать с собственным методом доступа или без него, например:

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

-или-

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

Обычно при вызове `CCommand::Open` (указание, например, в `CRowset` качестве `TRowset` класса) получает `IRowset` указатель. `ICommand::Execute` Возвращает `IRowset` указатель, хранящийся в элементе `m_spRowset` `CRowset` объекта. Такие методы `MoveFirst` , как, `MoveNext` , и `GetData` используют этот указатель для получения данных.

Напротив, при вызове `CCommand::Open` (но указании в `CStreamRowset` качестве `TRowset` класса) `ICommand::Execute` возвращает `ISequentialStream` указатель, который хранится в элементе `m_spStream` Data элемента [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Затем используйте `Read` метод для получения данных (строки в Юникоде) в формате XML. Пример:

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000 выполняет форматирование XML и возвращает все столбцы и все строки набора строк в виде одной строки XML.

Пример использования `Read` метода см. в разделе **Добавление поддержки XML к потребителю** при [реализации простого потребителя](../../data/oledb/implementing-a-simple-consumer.md).

> [!NOTE]
> Поддержка XML с использованием `CStreamRowset` работает только с SQL Server 2000 и требует наличия поставщика OLE DB для SQL Server 2000 (устанавливается вместе с MDAC).

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>Получение XML-данных с помощью CXMLAccessor

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) позволяет получать доступ к данным из источника данных в виде строковых данных, если нет сведений о схеме хранилища данных. `CXMLAccessor` работает `CDynamicStringAccessorW` , как за исключением того, что первый преобразует все данные, доступ к которым осуществлялся из хранилища данных, как данные в формате XML (с тегами). Имена XML-тегов совпадают с именами столбцов хранилища данных как можно точнее.

Используйте, `CXMLAccessor` как и любой другой класс метода доступа, передав его в качестве параметра шаблона в `CCommand` или `CTable` :

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

Используйте [жетксмлровдата](./cxmlaccessor-class.md#getxmlrowdata) для получения данных из таблицы по одной строке за раз и перехода по строкам с помощью таких методов `MoveNext` , как, например:

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

[Жетксмлколумндата](./cxmlaccessor-class.md#getxmlcolumndata) можно использовать для получения сведений о столбце (типе данных) в виде строковых данных в формате XML.

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)
