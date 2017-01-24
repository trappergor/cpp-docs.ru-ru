---
title: "db_column | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_column"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_column attribute"
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# db_column
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Привязывает указанный столбец к переменной в наборе строк.  
  
## Синтаксис  
  
```  
  
      [ db_column(   
   ordinal,   
   dbtype,   
   precision,   
   scale,   
   status,   
   length   
) ]  
```  
  
#### Параметры  
 `ordinal`  
 Порядковый номер столбца \(DBCOLUMNINFO порядковый номер\) или имя столбца \(строки ANSI или юникод\), соответствующее полю в наборе строк, в котором для привязки данных.  При использовании номера, можно пропустить последовательные порядковые номера \(например: 1, 2, 3, 5\).  Имя может содержать пробелы, если поставщик OLE DB, используемый поддерживает его.  Например, можно использовать любой из следующих форматов:  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *dbtype* \(необязательно\)  
 OLE DB [Индикатор типа](https://msdn.microsoft.com/en-us/library/ms711251.aspx) для записи столбца.  
  
 *Точность* \(необязательно\)  
 Точность, используемая для записи столбца.  Дополнительные сведения см. в разделе описание `bPrecision` элемент   [структура DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *масштаб* \(необязательно\)  
 Масштаб, используемый для записи столбца.  Дополнительные сведения см. в разделе описание `bScale` элемент   [структура DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *состояние* \(необязательно\)  
 Переменная\-член, используемая для хранения состояния данного столбца.  Состояние, указывающее, является ли значение столбца значение данных или другое значение, например **Значение NULL**.  Возможные значения см. [Состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в Справочник по программированию OLE DB.  
  
 *длина* \(необязательно\)  
 Переменная\-член, используемая для хранения размер столбца в байтах.  
  
## Заметки  
 **db\_column** связывает столбец указанной таблицы на переменную в наборе строк.  Он обозначает данные члена, которые могут участвовать в OLE DB `IAccessor`привязка на платформе.  Этот атрибут обычно настраивается сопоставление столбцов определяемое с помощью макросов объекта\-получателя OLE DB [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)"  [END\_COLUMN\_MAP](../data/oledb/end-column-map.md)и  [COLUMN\_ENTRY](../data/oledb/column-entry.md).  Они обрабатывают OLE DB [структура DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) привязать указанный столбец.  Каждый член пометить с **db\_column** атрибут займет одну запись в сопоставлении столбцов в форме записи столбца.  Поэтому следует вызывать этот атрибут, где необходимо поместить бы сопоставление столбцов, т е в команде или класс таблицы.  
  
 Используйте **db\_column** вместе с этим  [db\_table](../windows/db-table.md) OR  [db\_command](../windows/db-command.md) атрибуты.  
  
 Когда поставщик атрибута объекта\-получателя применяет этот атрибут к классу компилятор переименовывает класс, \_*YourClassName*метод доступа, где *YourClassName* имя указанного класса, и компилятор также создает класс *YourClassName,* что является производным от \_*YourClassName*метод доступа.  В представлении классов отобразится оба класса.  
  
 Примеры этого атрибута, используемого в приложении см. в разделе примеры [AtlAgent](http://msdn.microsoft.com/ru-ru/52bef5da-c1a0-4223-b4e6-9e464b6db409)и  [MultiRead](http://msdn.microsoft.com/ru-ru/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Пример  
 В этом образце связывает столбец в таблице к a long элемент данных и определяет поля состояния и длины.  
  
```  
// db_column_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   DBSTATUS m_dwProductIDStatus;  
   DBLENGTH m_dwProductIDLength;  
  
   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;  
};  
```  
  
## Пример  
 В этом образце привязывает 4 столбца к a **long**строка символов, отметку времени и a  **DB\_NUMERIC** целое число в другом порядке.  
  
```  
// db_column_2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   [db_column("1")] LONG m_OrderID;  
   [db_column("2")] TCHAR m_CustomerID[6];  
   [db_column("4")] DB_NUMERIC m_OrderDate;     
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`участник, метод|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)