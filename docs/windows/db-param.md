---
title: "db_param | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_param"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_param attribute"
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_param
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Связывает указанная переменная члена с входом или параметром вывода и отделяет переменную.  
  
## Синтаксис  
  
```  
  
      [ db_param(   
   ordinal,   
   paramtype="DBPARAMIO_INPUT",   
   dbtype,   
   precision,   
   scale,   
   status,   
   length  
) ]  
```  
  
#### Параметры  
 `ordinal`  
 Номер столбцаDBCOLUMNINFO порядковый номер\), соответствующее полю в наборе строк, в котором для привязки данных.  
  
 *paramtype* \(необязательно\)  
 Тип, которое нужно задать для параметра.  Поставщики поддерживают только типы ВВОДА\-ВЫВОДА параметра, поддерживаются базовым источником данных.  Тип сочетание одного или нескольких DBPARAMIOENUM значения:  
  
-   DBPARAMIO\_INPUT   входной параметр.  
  
-   DBPARAMIO\_OUTPUT   параметр вывода.  
  
-   DBPARAMIO\_NOTPARAM   Метод доступа не имеет параметров.  Установка eParamIO к этому значению в методах доступа строки напоминает пользователь, что параметры игнорируются.  
  
 *dbtype* \(необязательно\)  
 OLE DB [Индикатор типа](https://msdn.microsoft.com/en-us/library/ms711251.aspx) для записи столбца.  
  
 *Точность* \(необязательно\)  
 Точность, используемая для записи столбца.  Дополнительные сведения см. в разделе описание **bPrecision** элемент   [структура DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *масштаб* \(необязательно\)  
 Масштаб, используемый для записи столбца.  Дополнительные сведения см. в разделе описание **bScale** элемент   [структура DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *состояние* \(необязательно\)  
 Переменная\-член, используемая для хранения состояния данного столбца.  Состояние, указывающее, является ли значение столбца значение данных или другое значение, например **Значение NULL**.  Возможные значения см. [Состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в Справочник по программированию OLE DB.  
  
 *длина* \(необязательно\)  
 Переменная\-член, используемая для хранения размер столбца в байтах.  
  
## Заметки  
 **db\_param** задает параметры, используемые в командах; поэтому используется с  **db\_command**.  Например, можно использовать db\_param в параметры привязки в запросах или в хранимых процедурах SQL.  Параметры в хранимой процедуре обозначаются вопросительными знаками \(?\), и необходимо привязать элементы данных, в том порядке, в котором параметры появляются.  
  
 **db\_param** отделяет данные члена, которые могут участвовать в OLE DB  `ICommandWithParameters`привязка на платформе.  Он устанавливает параметр типа \(входной или выходной\), тип OLE DB, точность, масштаб, состояние и длину указанного параметра.  Этот атрибут вставляет макросы BEGIN\_PARAM\_MAP объекта\-получателя OLE DB…  END\_PARAM\_MAP.  Каждый член пометить с db\_param атрибут займет одну запись в сопоставлении в форме COLUMN\_ENTRY.  
  
 **db\_param** используется в сочетании с этим  [db\_table](../windows/db-table.md) OR  [db\_command](../windows/db-command.md) атрибуты.  
  
 Когда поставщик атрибута объекта\-получателя применяет этот атрибут к классу компилятор переименовывает класс, \_*YourClassName*метод доступа, где *YourClassName* имя указанного класса, и компилятор также создает класс *YourClassName,* что является производным от \_*YourClassName*метод доступа.  В представлении классов отобразится оба класса.  
  
## Пример  
 В следующем примере создается класс команды на основе хранимой процедуре SalesbyYear в базе данных Northwind.  Он связывает первый параметр в хранимой процедуре с `m_RETURN_VALUE` переменная и указывает его как параметр вывода.  Он связывает последние 2 параметра \(ввода\) `m_Beginning_Date` и  `m_Ending_Date`.  
  
 Следующий пример связывает `nOutput` переменная с параметром вывода.  
  
```  
// db_param.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_source(L"my_connection_string"),   
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")   
]  
struct CSalesbyYear {  
   DBSTATUS m_dwShippedDateStatus;  
   DBSTATUS m_dwOrderIDStatus;  
   DBSTATUS m_dwSubtotalStatus;  
   DBSTATUS m_dwYearStatus;  
  
   DBLENGTH m_dwShippedDateLength;  
   DBLENGTH m_dwOrderIDLength;  
   DBLENGTH m_dwSubtotalLength;  
   DBLENGTH m_dwYearLength;  
  
   // Bind columns  
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;  
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;  
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;  
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];  
  
   // Bind parameters  
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;  
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;  
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`участник, метод local|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)