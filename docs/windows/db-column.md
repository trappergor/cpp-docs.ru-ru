---
title: "db_column | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.db_column
dev_langs: C++
helpviewer_keywords: db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8fda1cfd5b23ae94da6be070e59add2854fb2687
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dbcolumn"></a>db_column
Связывает указанного столбца с переменной в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `ordinal`  
 Порядковый номер столбца (**DBCOLUMNINFO** порядковый номер) или имя столбца (строка ANSI или Юникод), соответствующее полю в наборе строк, к которому выполняется привязка данных. При использовании номера, можно пропустить последовательных порядковые номера (например: 1, 2, 3, 5). Имя может содержать пробелы, если используемый поставщик OLE DB поддерживает его. Например можно использовать любой из следующих форматов:  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *Тип DbType* (необязательно)  
 OLE DB [индикатор типа](https://msdn.microsoft.com/en-us/library/ms711251.aspx) для записи в столбце.  
  
 *точность* (необязательно)  
 Точность, используемый для записи в столбце. Дополнительные сведения см. в описании `bPrecision` элемент [структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Масштаб* (необязательно)  
 Масштаб, используемый для записи в столбце. Дополнительные сведения см. в описании `bScale` элемент [структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *состояние* (необязательно)  
 Член переменной, используемой для хранения состояния этого столбца. Состояние указывает, является ли значение столбца значение данных или любое другое значение, таких как **NULL**. Возможные значения см. в разделе [состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в *Справочник программиста OLE DB*.  
  
 *Длина* (необязательно)  
 Член переменной, используемой для хранения размер столбца в байтах.  
  
## <a name="remarks"></a>Примечания  
 **db_column** связывает указанного табличного столбца с переменной в наборе строк. Она разделяет данные члена, которые могут участвовать в OLE DB `IAccessor`-привязку на основе. Этот атрибут задает сопоставление столбцов, обычно определяется с помощью макросов потребителя OLE DB [BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../data/oledb/end-column-map.md), и [COLUMN_ENTRY](../data/oledb/column-entry.md). Эти работы с OLE DB [структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) для привязки указанного столбца. Каждый член, пометьте с **db_column** атрибут будет занимать одну запись в карте столбцов в виде записи в столбце. Таким образом вызов этого атрибута будет размещения сопоставление столбцов, то есть в классе команд или таблиц.  
  
 Используйте **db_column** вместе с любой [db_table](../windows/db-table.md) или [db_command](../windows/db-command.md) атрибуты.  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор будет Переименуйте класс в \_ *имя_класса*метод доступа, где *имя_класса* является названием также создайте класс с именем класса и компилятор *имя_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
 Примеры этого атрибута, используемого в приложении, см. Образцы [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409), и [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Пример  
 В этом примере привязки к столбцу в таблице, чтобы **длинные** элемент данных и указывает состояния и длины поля.  
  
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
  
## <a name="example"></a>Пример  
 В этом примере привязывает четыре столбца, чтобы **длинные**, символьная строка, отметку времени и **DB_NUMERIC** целое число со знаком в указанном порядке.  
  
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
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс**, `struct`, элемент, метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
