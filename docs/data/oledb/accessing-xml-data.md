---
title: "Доступ к данным XML | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset - класс, извлечение данных XML"
  - "CXMLAccessor - класс, извлечение данных XML"
  - "данные [C++], доступ к данным XML"
  - "доступ к данным [C++], данные XML"
  - "наборы строк [C++], извлечение данных XML"
  - "XML [C++], доступ к данным"
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Доступ к данным XML
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Существует два способа получения данных XML из источника: с использованием [CStreamRowset](../../data/oledb/cstreamrowset-class.md) или [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  
  
|Функциональная возможность|CStreamRowset|CXMLAccessor|  
|--------------------------------|-------------------|------------------|  
|Количество переданных данных|Одновременное получение данных из всех столбцов и строк.|Получение данных из всех столбцов, но только одной строки за один раз.  Необходимо переходить между строками, используя такие методы, как `MoveNext`.|  
|Форматирование строки|SQL Server форматирует строку XML и отправляет ее объекту\-получателю.|Получение данных набора строк в собственном формате \(для этого требуется, чтобы поставщик отправил их в виде строк в кодировке Юникода\) и построение строки, содержащей данные в формате XML.|  
|Управление форматированием|Существует несколько уровней управления форматированием строки XML, настраиваемых с помощью настройки свойств SQL Server 2000.|Управление форматированием создаваемой строки XML недоступно.|  
  
 В то время как `CStreamRowset` предоставляет более эффективный способ получения данных в формате XML, он поддерживается только SQL Server 2000.  
  
## Получение данных XML с помощью CStreamRowset  
 В объявлении `CCommand` или `CTable` в качестве типа набора строк пользователь указывает [CStreamRowset](../../data/oledb/cstreamrowset-class.md).  Его можно использовать с методом доступа или без него, например:  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 – или –  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 Обычно при вызове `CCommand::Open` \(с указанием, например, `CRowset` в качестве класса `TRowset`\), он получает указатель `IRowset`.  `ICommand::Execute` возвращает указатель `IRowset`, который хранится в элементе `m_spRowset` объекта `CRowset`.  Методы, например `MoveFirst`, `MoveNext` и `GetData`, используют этот указатель для получения данных.  
  
 С другой стороны, при вызове `CCommand::Open` \(но с указанием `CStreamRowset` в качестве класса `TRowset`\), `ICommand::Execute` возвращает указатель `ISequentialStream`, который хранится в элементе данных `m_spStream` объекта [CStreamRowset](../../data/oledb/cstreamrowset-class.md).  После этого используется метод `Read`, чтобы получить данные \(строки в кодировке Юникода\) в формате XML.  Примеры.  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 выполняет форматирование XML и возвращает все столбцы и строки набора как одну строку XML.  
  
 Пример использования метода `Read` см. в подразделе "Добавление поддержки XML в объект\-получатель" раздела [Реализация простого объекта\-получателя](../../data/oledb/implementing-a-simple-consumer.md).  
  
> [!NOTE]
>  Поддержка XML с использованием `CStreamRowset` доступна только для SQL Server 2000 и требует поставщика OLE DB для SQL Server 2000 \(установленного с компонентами MDAC\).  
  
## Получение данных XML с помощью CXMLAccessor  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) позволяет получить доступ к данным из источника данных в виде строковых данных в случае, если отсутствует информация о схеме хранилища данных.  `CXMLAccessor` действует как `CDynamicStringAccessorW` с той только разницей, что первый преобразует все данные из хранилища в формат XML \(с тегами\).  Имена тегов XML совпадают с названиями столбцов хранилища данных насколько это возможно.  
  
 Воспользуйтесь `CXMLAccessor` как любым другим классом доступа, передав его как параметр шаблона в `CCommand` или `CTable`:  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 Используйте [GetXMLRowData](../Topic/CXMLAccessor::GetXMLRowData.md), чтобы получить данные из одной строки таблицы за один раз, и переходите между строками с помощью методов, таких как `MoveNext`, например:  
  
```  
// Open data source, session, and rowset  
hr = rs.MoveFirst();  
while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
{  
    CStringW strRowData;  
    myCmd.GetXMLRowData(strRowData);  
  
    printf_s( "%S\n", strRowData );  
  
    hr = rs.MoveNext();  
}  
```  
  
 Чтобы получить информацию столбца \(типа данных\) как строковые данные в формате XML, воспользуйтесь [GetXMLColumnData](../Topic/CXMLAccessor::GetXMLColumnData.md).  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)