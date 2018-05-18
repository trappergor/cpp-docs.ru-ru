---
title: db_param | Документы Microsoft
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
ms.openlocfilehash: ce7cf5c8e92e7fd6e6e10d7bef0519b1ced4cf62
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="dbparam"></a>db_param
Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `ordinal`  
 Номер столбца (**DBCOLUMNINFO** порядковый номер) в поле в наборе строк, к которому выполняется привязка данных.  
  
 *paramtype* (необязательно)  
 Тип, задаваемый для параметра. Поставщики поддерживают только ввода-вывода типов параметров, поддерживаемых в источнике данных. Тип представляет собой сочетание одного или нескольких **DBPARAMIOENUM** значения:  
  
-   **DBPARAMIO_INPUT** Входной параметр  
  
-   **DBPARAMIO_OUTPUT** Выходной параметр  
  
-   **DBPARAMIO_NOTPARAM** Метод доступа не имеет параметров. Установка **eParamIO** это значение в строке доступа к свойствам напоминает пользователям, что параметры игнорируются.  
  
 *Тип DbType* (необязательно)  
 OLE DB [индикатор типа](https://msdn.microsoft.com/en-us/library/ms711251.aspx) для записи в столбце.  
  
 *точность* (необязательно)  
 Точность, используемый для записи в столбце. Дополнительные сведения см. в описании **bPrecision** элемент [структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Масштаб* (необязательно)  
 Масштаб, используемый для записи в столбце. Дополнительные сведения см. в описании **bScale** элемент [структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *состояние* (необязательно)  
 Член переменной, используемой для хранения состояния этого столбца. Состояние указывает, является ли значение столбца значение данных или любое другое значение, таких как **NULL**. Возможные значения см. в разделе [состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в *Справочник программиста OLE DB*.  
  
 *Длина* (необязательно)  
 Член переменной, используемой для хранения размер столбца в байтах.  
  
## <a name="remarks"></a>Примечания  
 **db_param** определяет параметры, что использование в командах; поэтому использовать его с **db_command**. Например, можно использовать **db_param** для привязки параметров в запросах SQL или хранимые процедуры. Параметры в хранимой процедуре, обозначаются вопросительные знаки (?), и необходимо привязать данные-члены в том порядке, в котором параметры появляются.  
  
 **db_param** разделяет данные члена, которые могут участвовать в OLE DB `ICommandWithParameters`-привязку на основе. Он задает тип параметра (входящих или исходящих), тип OLE DB, точность, масштаб, состояния и длины для указанного параметра. Этот атрибут вставляет макросы потребителя OLE DB BEGIN_PARAM_MAP... END_PARAM_MAP. Каждый член, пометьте с **db_param** атрибут будет занимать одну запись в схеме в виде COLUMN_ENTRY.  
  
 **db_param** используется в сочетании с любой [db_table](../windows/db-table.md) или [db_command](../windows/db-command.md) атрибуты.  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор будет Переименуйте класс в \_ *имя_класса*метод доступа, где *имя_класса* является названием также создайте класс с именем класса и компилятор *имя_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
## <a name="example"></a>Пример  
 В следующем примере создается класс команд, основанный на SalesbyYear хранимой процедуры в базе данных Northwind. Он связывает первого параметра в хранимую процедуру с `m_RETURN_VALUE` переменной и определяет его как выходной параметр. Он связывает последние два параметра (входной) с `m_Beginning_Date` и `m_Ending_Date`.  
  
 В следующем примере производится связывание `nOutput` переменную с выходным параметром.  
  
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
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`, member, method, local|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты объекта-получателя OLE DB](../windows/ole-db-consumer-attributes.md)   
