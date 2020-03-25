---
title: Определение хранимых процедур
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
ms.openlocfilehash: 9bab086bf6982eae5779d3199cfd2ac2c8efe77f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211008"
---
# <a name="defining-stored-procedures"></a>Определение хранимых процедур

Перед вызовом хранимой процедуры необходимо сначала определить ее с помощью макроса [DEFINE_COMMAND](../../data/oledb/define-command.md) . При определении команды обопомните параметры с вопросительным знаком (?) в качестве маркера параметра:

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{INSERT {name, phone} INTO shippers (?,?)}"))
```

Синтаксис (использование фигурных скобок и т. д.), используемый в примерах кода в этом разделе, относится только к SQL Server. Синтаксис, используемый в хранимых процедурах, может отличаться в зависимости от используемого поставщика.

Затем на карте параметров укажите параметры, которые использовались в команде, и перечислите параметры в том порядке, в котором они встречаются в команде.

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param
END_PARAM_MAP()
```

В предыдущем примере хранимая процедура определяется по мере того, как она происходит. Как правило, для эффективного повторного использования кода база данных содержит набор предопределенных хранимых процедур с такими именами, как `Sales by Year` или `dt_adduserobject`. Их определения можно просмотреть с помощью диспетчера SQL Server Enterprise. Их можно вызвать следующим образом (расположение *?* параметры зависят от интерфейса хранимой процедуры):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }"))
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }"))
```

Затем объявите класс Command:

```cpp
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>
```

Наконец, вызовите хранимую процедуру в `OpenRowset` следующим образом:

```cpp
CSession m_session;

HRESULT OpenRowset()
{
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);
}
```

Также обратите внимание, что хранимую процедуру можно определить с помощью атрибута базы данных [db_command](../../windows/db-command.md) следующим образом:

```cpp
db_command("{ ? = CALL dbo.dt_adduserobject }")
```

## <a name="see-also"></a>См. также раздел

[Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)
