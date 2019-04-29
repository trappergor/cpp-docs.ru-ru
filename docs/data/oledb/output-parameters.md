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
ms.openlocfilehash: 196c50ea62c3e3188b61a3b35a9e2752740c4ad5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283975"
---
# <a name="output-parameters"></a>Выходные параметры

Вызов хранимой процедуры аналогична команды SQL. Основное различие — что хранимые процедуры используйте параметры выходных данных (или «выходные параметры») и возвращаемых значений.

В следующем примере хранимая процедура, первый "? «является возвращаемым значением (phone), а второй»?" является входным параметром (имя):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

Необходимо указать входные и выходные параметры в сопоставлении параметров:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

Приложение должно обрабатывать выходные данные, возвращаемые хранимыми процедурами. Различные поставщики OLE DB возвращают выходные параметры и возвращаемые значения на различных этапах обработки результатов. Например поставщик Microsoft OLE DB для SQL Server (SQLOLEDB) не предоставляет выходные параметры и коды возвращения до тех потребитель получит или отменено результирующие наборы, возвращаемые хранимой процедурой. Выходные данные возвращаются в последнем пакете потока табличных данных с сервера.

## <a name="row-count"></a>Число строк

При использовании шаблонов потребителей OLE DB для выполнения хранимой процедуры, имеющей выходные параметры, количество строк не задается, пока вы не закроете набора строк.

Например рассмотрим хранимой процедуры с набором строк и выходными параметрами:

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

`@_rowcount` Параметр сообщает, сколько строк были возвращены из тестовой таблицы. Тем не менее эта хранимая процедура ограничивает число строк до 50. Например если бы он был 100 строк в тесте, количество строк будет 50 (так как этот код извлекает только первые 50 строк). Если только 30 строк в таблице, количество строк будет 30. Не забудьте вызвать `Close` или `CloseAll` чтобы заполнить параметр до извлечения его значения.

## <a name="see-also"></a>См. также

[Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)