---
title: db_column | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_column
dev_langs:
- C++
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20c651c6e671c7c4895fc7dba85d16fdeb998ad5
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570705"
---
# <a name="dbcolumn"></a>db_column
Привязывает указанный столбец к переменной в наборе строк.  
  
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
 *Порядковый номер*  
 Порядковый номер столбца (`DBCOLUMNINFO` порядковый номер) или имя столбца (строка ANSI или Юникод), соответствующее поле в наборе строк, к которому требуется привязать данные. Если вы используете номера, можно пропустить последовательных порядковые номера (например: 1, 2, 3, 5). Имя может содержать пробелы, если используемый поставщик OLE DB поддерживает его. Например можно использовать любой из следующих форматов:  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
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
 **db_column** связывает указанного табличного столбца с переменной в наборе строк. Она разделяет данные члена, которые могут участвовать в OLE DB `IAccessor`-привязку на основе. Этот атрибут задает сопоставление столбцов, обычно определяется с помощью макросов потребителя OLE DB [BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../data/oledb/end-column-map.md), и [COLUMN_ENTRY](../data/oledb/column-entry.md). Эти управления OLE DB [структуры DBBINDING](https://msdn.microsoft.com/library/ms716845.aspx) для привязки указанного столбца. Каждый член, пометьте с **db_column** атрибут будет занимать одну запись в сопоставлении столбцов в виде записи в столбце. Следовательно вызывать этот атрибут где находится в сопоставление столбцов, то есть в классе команд или таблиц.  
  
 Используйте **db_column** в сочетании со [db_table](../windows/db-table.md) или [db_command](../windows/db-command.md) атрибуты.  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс \_ *Имя_вашего_класса*метод доступа, где *Имя_вашего_класса* — это имя, присвоенное класс, компилятор также создаст класс с именем *Имя_вашего_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
 Примеры использования этого атрибута, используемые в приложениях, см. Примеры [AtlAgent](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409), и [MultiRead](http://msdn.microsoft.com/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Пример  
 В этом образце привязки к столбцу в таблице, чтобы **long** член данных с указанием состояния и длины поля.  
  
```cpp  
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
 В этом примере привязывает четыре столбца, **long**, символьная строка, метку времени и `DB_NUMERIC` целое число, в указанном порядке.  
  
```cpp  
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
|**Применение**|**Класс**, **структуры**, элемент, метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   