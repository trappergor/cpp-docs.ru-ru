---
title: Класс ICommandImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandImpl class
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d69ff56ec92fd3acb622aa4c0399893fb44c4d1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101147"
---
# <a name="icommandimpl-class"></a>Класс ICommandImpl
Предоставляет реализацию для [ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `ICommandImpl`.  
  
 `CommandBase`  
 Интерфейс команды. Значение по умолчанию — `ICommand`.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)|Отмена выполнения текущей команды.|  
|[Отмена](../../data/oledb/icommandimpl-cancel.md)|Отмена выполнения текущей команды.|  
|[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)|Создает объект набора строк.|  
|[Выполнение](../../data/oledb/icommandimpl-execute.md)|Выполняет команду.|  
|[GetDBSession](../../data/oledb/icommandimpl-getdbsession.md)|Возвращает указатель на интерфейс для сеанса, создавшего команду.|  
|[ICommandImpl](../../data/oledb/icommandimpl-icommandimpl.md)|Конструктор.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)|Указывает, является ли команда отменяется.|  
|[m_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)|Указывает, является ли отменяется при выполнении команды.|  
|[m_bIsExecuting](../../data/oledb/icommandimpl-m-bisexecuting.md)|Указывает, является ли команда в данный момент.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс для объекта команды.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)