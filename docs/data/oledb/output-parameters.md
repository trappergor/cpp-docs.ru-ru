---
title: Выходные параметры
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
ms.openlocfilehash: ece626eb7fbecae9b90321ccc2569607897cf520
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209863"
---
# <a name="output-parameters"></a>Выходные параметры

Вызов хранимой процедуры аналогичен выполнению команды SQL. Основное различие заключается в том, что хранимые процедуры используют выходные параметры (или «параметры») и возвращаемые значения.

В следующей хранимой процедуре первым "?" является возвращаемым значением (Phone), а второй "?" — входным параметром (Name):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

Вы указываете параметры in и out в сопоставлении параметров:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

Приложение должно выполнять обработку выходных данных, возвращаемых хранимыми процедурами. Разные поставщики OLE DB возвращают выходные параметры и значения на разных этапах во время обработки результатов. Например, поставщик Microsoft OLE DB для SQL Server (SQLOLEDB) не предоставляет выходные параметры и коды возврата до тех пор, пока потребитель не извлек или не отменил результирующие наборы, возвращенные хранимой процедурой. Выходные данные возвращаются в последнем пакете TDS с сервера.

## <a name="row-count"></a>Количество строк

Если для выполнения хранимой процедуры с параметрами используются шаблоны потребителей OLE DB, количество строк не будет задано до тех пор, пока набор строк не будет закрыт.

Например, рассмотрим хранимую процедуру с набором строк и параметром.

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

Параметр `@_rowcount` параметры сообщает, сколько строк было возвращено из тестовой таблицы. Однако эта хранимая процедура ограничивает число строк до 50. Например, если в тесте 100 строк, то значение ROWCOUNT будет равно 50 (поскольку этот код извлекает только первые 50 строк). Если в таблице было всего 30 строк, то значение ROWCOUNT будет равно 30. Не забудьте вызвать `Close` или `CloseAll`, чтобы заполнить параметр перед получением его значения.

## <a name="see-also"></a>См. также раздел

[Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)
