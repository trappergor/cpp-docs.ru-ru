---
title: Определение хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9d5cbe04ac5ad23fef09d53e747dab8c4c4b53b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053141"
---
# <a name="defining-stored-procedures"></a>Определение хранимых процедур

Перед вызовом хранимой процедуры, необходимо сначала определить, с помощью [DEFINE_COMMAND](../../data/oledb/define-command.md) макрос. При определении команда обозначения параметров знаком вопроса (?), как маркер параметров:

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{INSERT {name, phone} INTO shippers (?,?)}"))
```

Синтаксис (Использование фигурных скобок и т. д.), который используется в примерах кода в этом разделе относится только к SQL Server. Синтаксис, который используется в хранимых процедурах может различаться в зависимости от поставщика, которые можно использовать.

Затем в сопоставлении параметров, укажите параметры, которые вы использовали в команде со списком параметров в порядке их появления в команде:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param
END_PARAM_MAP()
```

Он определяется хранимой процедуры в предыдущем примере. Как правило, для эффективного повторного использования кода, база данных содержит набор стандартные хранимые процедуры с именами, такие как `Sales by Year` или `dt_adduserobject`. Вы можете просмотреть их определения, с помощью SQL Server Enterprise Manager. Можно вызвать следующим образом (размещение *?* параметры зависят от интерфейса хранимых процедур):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }"))
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }"))
```

Объявите класс команд:

```cpp
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>
```

Наконец, вызовите хранимую процедуру `OpenRowset` следующим образом:

```cpp
CSession m_session;

HRESULT OpenRowset()
{
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);
}
```

Также Обратите внимание, что хранимую процедуру при помощи атрибута базы данных можно определить [db_command](../../windows/db-command.md) следующим образом:

```cpp
db_command("{ ? = CALL dbo.dt_adduserobject }")
```

## <a name="see-also"></a>См. также

[Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)