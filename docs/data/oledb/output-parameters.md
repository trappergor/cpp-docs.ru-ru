---
title: Выходные параметры | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8733b967ddab7e6f68fcbee1c80e78500a679f96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="output-parameters"></a>Выходные параметры
Вызов хранимой процедуры похож на вызов команды SQL. Основное отличие является параметры выходных данных (или «выходные параметры») хранимых процедур и возвращаемые значения.  
  
 В следующем примере хранимая процедура, первый "? «является возвращаемым значением (phone), а вторым»?" — это входной параметр (имя):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 Укажите и выходные параметры в сопоставлении параметров:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 Приложение должно обрабатывать выходные данные, возвращаемые хранимыми процедурами. Различные поставщики OLE DB возвращают выходные параметры и возвращаемые значения на различных этапах обработки результатов. Например поставщик Microsoft OLE DB для SQL Server (SQLOLEDB) не предоставляет выходные параметры и коды возвращения до тех потребитель получит или отменит результирующие наборы, возвращаемые хранимой процедурой. Выходные данные возвращаются в последнем пакете потока табличных данных с сервера.  
  
## <a name="row-count"></a>Число строк  
 При использовании шаблонов потребителей OLE DB для выполнения хранимой процедуры, имеющей выходные параметры, количество строк не задано до выхода из набора строк.  
  
 Например рассмотрим хранимой процедуры с набором строк и выходными параметрами.  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @_rowcount Параметр сообщает, сколько строк было фактически возвращено из тестовой таблицы. Тем не менее эта хранимая процедура ограничивает число строк до 50. Например если в тесте 100 строк, количество строк будет 50 (поскольку код извлекает только первые 50 строк). Если только 30 строк в таблице, количество строк будет 30. Необходимо вызвать **закрыть** или **CloseAll** чтобы заполнить параметр до извлечения его значения.  
  
## <a name="see-also"></a>См. также  
 [Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)