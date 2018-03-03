---
title: "db_accessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.db_accessor
dev_langs:
- C++
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5faa84773fbf1fe15fd0223c97f0361f1215b149
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dbaccessor"></a>db_accessor
Группы **db_column** атрибутов, участвующих в `IAccessor`-привязку на основе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *num*  
 Указывает номер доступа (отсчитываемый от нуля целочисленного индекса). Необходимо указать номера доступа в увеличение заказ, используя целые числа или определенные значения.  
  
 *auto*  
 Логическое значение, указывающее, является ли метод доступа автоматически извлекается (**TRUE**) или не получены (**FALSE**).  
  
## <a name="remarks"></a>Примечания  
 **db_accessor** определяет базовый метод доступа OLE DB для последующих **db_column** и **db_param** атрибутов в том же классе или функции. **db_accessor** можно использовать на уровне элемента и используется в группу **db_column** атрибутов, участвующих в OLE DB `IAccessor`-привязку на основе. Он используется в сочетании с любой **db_table** или **db_command** атрибуты. Вызов этого атрибута аналогично вызову [BEGIN_ACCESSOR](../data/oledb/begin-accessor.md) и [END_ACCESSOR](../data/oledb/end-accessor.md) макросы.  
  
 **db_accessor** создает набор строк и привязывает его к соответствующей сопоставления доступа. Если вы не вызываете **db_accessor**, метод доступа 0 будет автоматически создан и привязки всех столбцов будет сопоставлено этот блок метода доступа.  
  
 **db_accessor** группы базы данных привязки столбцов в один или несколько методов доступа. Обсуждение сценариев, в которых необходимо использовать несколько методов доступа см. в разделе [с помощью нескольких методов доступа в наборе строк](../data/oledb/using-multiple-accessors-on-a-rowset.md). Также в разделе «Пользователь запись поддержки для нескольких методов доступа» в [записей пользователей](../data/oledb/user-records.md).  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор будет Переименуйте класс в \_ *имя_класса*метод доступа, где *имя_класса* является названием также создайте класс с именем класса и компилятор *имя_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
## <a name="example"></a>Пример  
 В следующем примере используется **db_accessor** Группировка столбцов в таблице Orders в базе данных "Борей" в двух методов доступа. Метод доступа 0 является автоматическим, а метод доступа 1 не.  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Блоки атрибутов|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты объекта-получателя OLE DB](../windows/ole-db-consumer-attributes.md)   
