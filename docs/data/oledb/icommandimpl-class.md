---
title: "Класс ICommandImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ICommandImpl
dev_langs: C++
helpviewer_keywords: ICommandImpl class
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ab3aced3ebd5c98699b967300b3a47d5171a74d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="icommandimpl-class"></a>Класс ICommandImpl
Предоставляет реализацию для [ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `ICommandImpl`.  
  
 `CommandBase`  
 Интерфейс команды. Значение по умолчанию — `ICommand`.  
  
## <a name="members"></a>Члены  
  
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