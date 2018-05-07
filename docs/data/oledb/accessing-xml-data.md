---
title: Доступ к данным XML | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3abe00adee2a88d0414d688984232422a5bcfc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-xml-data"></a>Доступ к данным XML
Существует два отдельных метода получения XML-данных из источника данных: одна использует [CStreamRowset](../../data/oledb/cstreamrowset-class.md) и для других целей [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  
  
|Функция|CStreamRowset|CXMLAccessor|  
|-------------------|-------------------|------------------|  
|Объем передаваемых данных|Извлекает данные из всех столбцов и строк за один раз.|Извлекает данные из всех столбцов, но только одну строку за один раз. Необходимо переходить между строками с помощью методов, таких как `MoveNext`.|  
|Строка форматирования|SQL Server форматирует строку XML и отправляет его получателю.|Получение данных набора строк в его собственном формате (запросы, которые поставщик отправил их как строки в Юникоде) и затем создает строку, содержащую данные в формате XML.|  
|Контроль над форматированием|У вас более высокий уровень контроля над форматом XML-строки, задав некоторые свойства связанные с SQL Server 2000.|У вас нет контроля над форматом созданный XML-строки.|  
  
 Хотя `CStreamRowset` обеспечивает более эффективный способ получения данных в формате XML, он поддерживается только для SQL Server 2000.  
  
## <a name="retrieving-xml-data-using-cstreamrowset"></a>Получение XML-данных с помощью CStreamRowset  
 Указать [CStreamRowset](../../data/oledb/cstreamrowset-class.md) набора строк в качестве типа вашего `CCommand` или `CTable` объявления. Он используется с методом доступа или без него, например:  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 - или -  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 Обычно при вызове `CCommand::Open` (указание, например, `CRowset` как `TRowset` класса), он получает `IRowset` указателя. `ICommand::Execute` Возвращает `IRowset` указатель, который хранится в `m_spRowset` членом `CRowset` объекта. Такие методы, как `MoveFirst`, `MoveNext`, и `GetData` используют этот указатель для получения данных.  
  
 В отличие от этого, при вызове `CCommand::Open` (но указать `CStreamRowset` как `TRowset` класса), `ICommand::Execute` возвращает `ISequentialStream` указатель, который хранится в `m_spStream` данными-членом [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Затем используйте `Read` метод для извлечения данных (строка в Юникоде) в формате XML. Пример:  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 выполняет форматирование XML и возвращает все столбцы и строки набора как одну строку XML.  
  
 Пример использования `Read` метод, содержатся в разделе «Добавление XML поддержки в код потребителя» [реализация простых объектов получателей](../../data/oledb/implementing-a-simple-consumer.md).  
  
> [!NOTE]
>  Поддержка XML с использованием `CStreamRowset` работает только с SQL Server 2000 и требует наличия поставщика OLE DB для SQL Server 2000 (устанавливается с компонентами MDAC).  
  
## <a name="retrieving-xml-data-using-cxmlaccessor"></a>Получение XML-данных с помощью CXMLAccessor  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) позволяет обращаться к данным из источника данных как строковые данные при наличии отсутствует информация о схеме хранилища данных. `CXMLAccessor` работает аналогично `CDynamicStringAccessorW` за исключением того, что первый преобразует все данные из хранилища данных в виде XML-данных (с тегом). Имена тегов XML как можно точнее соответствовать имена столбцов в хранилище данных.  
  
 Используйте `CXMLAccessor` как и любого другого метода доступа класса, передавая его как параметр шаблона для `CCommand` или `CTable`:  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 Используйте [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) для получения данных из одной строки таблицы во время и перемещения строк с помощью методов, таких как `MoveNext`, например:  
  
```  
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
  
 Можно использовать [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) получить сведения о столбцах (тип данных) как строковые данные в формате XML.  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)