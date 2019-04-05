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
ms.openlocfilehash: b5704c10393026a14ac66b632559fc376f008f8b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041540"
---
# <a name="accessing-xml-data"></a>Доступ к данным XML

Существует два различных метода получения XML-данных из источника данных: одна использует [CStreamRowset](../../data/oledb/cstreamrowset-class.md) и с помощью [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).

|Функция|Класс CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|Объем переданных данных|Извлекает данные из всех столбцов и строк за один раз.|Извлекает данные из всех столбцов, но только одну строку за раз. Вам нужно перейти с помощью методов, таких как строки `MoveNext`.|
|Строка форматирования|SQL Server форматирует строку XML и отправляет его получателю.|Извлекает данные набора строк в его собственном формате (запросы, которые поставщик отправить его как строки в Юникоде) и затем создает строку, которая хранит данные в формате XML.|
|Управление форматированием|У вас есть определенный уровень контроля над форматом XML-строки, задав некоторые свойства связанные с SQL Server 2000.|У вас нет контроля над форматом созданный XML-строки.|

Хотя `CStreamRowset` предоставляет более эффективный способ получения данных в формате XML, он поддерживается только SQL Server 2000.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>Получение данных XML, с помощью CStreamRowset

Указать [CStreamRowset](../../data/oledb/cstreamrowset-class.md) набора строк в качестве типа вашего `CCommand` или `CTable` объявления. Можно использовать его с методом доступа или без него, например:

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

- или -

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

Обычно при вызове `CCommand::Open` (указание, например, `CRowset` как `TRowset` класс), он получает `IRowset` указатель. `ICommand::Execute` Возвращает `IRowset` указатель, который хранится в `m_spRowset` членом `CRowset` объекта. Методы, такие как `MoveFirst`, `MoveNext`, и `GetData` используют этот указатель для получения данных.

Напротив, при вызове `CCommand::Open` (но указать `CStreamRowset` как `TRowset` класс), `ICommand::Execute` возвращает `ISequentialStream` указатель, который хранится в `m_spStream` данными-членом [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Затем используйте `Read` метод для извлечения данных (строка Юникод) в формате XML. Пример:

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000 не XML-форматирование и возвращает все столбцы и строки набора строк как одну строку XML.

В качестве примера использования `Read` метод, см. в разделе **Добавление поддержки XML в потребитель** в [реализация простых объектов получателей](../../data/oledb/implementing-a-simple-consumer.md).

> [!NOTE]
> Поддержка XML с использованием `CStreamRowset` работает только с SQL Server 2000 и требуется наличие поставщика OLE DB для SQL Server 2000 (установлена с компонентами MDAC).

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>Получение данных XML, с помощью CXMLAccessor

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) позволяет получить доступ к данным из источника данных как строковые данные при наличии схема хранилища данных. `CXMLAccessor` работает аналогично `CDynamicStringAccessorW` за исключением того, что первый преобразует все данные из хранилища данных в виде XML-данных (с тегами). Имена тегов XML, как можно точнее соответствовать имена столбцов в хранилище данных.

Используйте `CXMLAccessor` как и любого другого метода доступа класса, передавая его как параметр шаблона для `CCommand` или `CTable`:

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

Используйте [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) для получения данных из одной строки таблицы за раз и перемещения строк с помощью методов, таких как `MoveNext`, например:

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

Можно использовать [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) получить сведения о столбцах (тип данных), как строковые данные в формате XML.

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)