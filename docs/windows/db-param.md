---
title: db_param | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_param
dev_langs:
- C++
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f9938f96e65053d396cdfb608bea1e21eb1df74
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651386"
---
# <a name="dbparam"></a>db_param
Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
### <a name="parameters"></a>Параметры  
 *Порядковый номер*  
 Номер столбца (порядковый номер DBCOLUMNINFO), соответствующее полю в наборе строк, к которому требуется привязать данные.  
  
 *paramtype* (необязательно)  
 Тип, задаваемый для параметра. Поставщики поддерживают только параметр типы ввода-вывода, поддерживаемые в базовом источнике данных. Тип представляет собой сочетание одного или нескольких значений DBPARAMIOENUM:  
  
-   DBPARAMIO_INPUT входного параметра.  
  
-   DBPARAMIO_OUTPUT выходной параметр.  
  
-   DBPARAMIO_NOTPARAM метод доступа не имеет параметров. Параметр `eParamIO` этому значению в строке методы доступа напоминает пользователям, что параметры игнорируются.  
  
 *dbType* (необязательно)  
 OLE DB [индикатор типа](https://msdn.microsoft.com/library/ms711251.aspx) для записи в столбце.  
  
 *точность* (необязательно)  
 Точность должна использоваться для записи в столбце. Дополнительные сведения см. в описании `bPrecision` элемент [структуры DBBINDING](https://msdn.microsoft.com/library/ms716845.aspx)  
  
 *Масштаб* (необязательно)  
 Масштабирования, которая будет использоваться для записи в столбце. Дополнительные сведения см. в описании `bScale` элемент [структуры DBBINDING](https://msdn.microsoft.com/library/ms716845.aspx)  
  
 *состояние* (необязательно)  
 Переменную-член используется для хранения состояния этого столбца. Состояние указывает, является ли значение столбца значение данных или любое другое значение, например значений NULL. Возможные значения см. в разделе [состояние](https://msdn.microsoft.com/library/ms722617.aspx) в *Справочник программиста OLE DB по*.  
  
 *Длина* (необязательно)  
 Переменную-член используется для хранения размера столбца в байтах.  
  
## <a name="remarks"></a>Примечания  
 **db_param** определяет параметры, что использовать в командах; поэтому использовать его с `db_command`. Например, можно использовать **db_param** для привязки параметров в запросах SQL или хранимые процедуры. Параметры в хранимой процедуре отмечены пометками вопросительные знаки (?), и необходимо привязать элементы данных в порядке, в котором параметры появляются.  
  
 **db_param** разделяет данные члена, которые могут участвовать в OLE DB `ICommandWithParameters`-привязку на основе. Он задает тип параметра (входной или выходной), тип OLE DB, точность, масштаб, состояния и длины для указанного параметра. Этот атрибут вставляет макросы потребителя OLE DB BEGIN_PARAM_MAP... END_PARAM_MAP. Каждый член, пометьте с **db_param** атрибут в схеме в виде COLUMN_ENTRY займет одну запись.  
  
 **db_param** используется в сочетании с любым [db_table](../windows/db-table.md) или [db_command](../windows/db-command.md) атрибуты.  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс \_ *Имя_вашего_класса*метод доступа, где *Имя_вашего_класса* — это имя, присвоенное класс, компилятор также создаст класс с именем *Имя_вашего_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
## <a name="example"></a>Пример  
 В следующем примере создается класс команд, основана на процедуре SalesbyYear хранятся в базе данных "Борей". Он связывает первого параметра в хранимую процедуру с `m_RETURN_VALUE` переменной и определяет его как выходной параметр. Он связывает последние два параметра (входной) с `m_Beginning_Date` и `m_Ending_Date`.  
  
 В следующем примере связываются `nOutput` переменную с выходным параметром.  
  
```cpp  
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
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс**, **структуры**, член, метод, локальный|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты объекта-получателя OLE DB](../windows/ole-db-consumer-attributes.md)   