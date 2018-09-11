---
title: Класс IDBCreateCommandImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b67fc55a8af2bed554254732832cbd6486d2420
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571712"
---
# <a name="idbcreatecommandimpl-class"></a>Класс IDBCreateCommandImpl
Предоставляет реализацию [IDBCreateCommand](/previous-versions/windows/desktop/ms711625\(v=vs.85\)) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class CommandClass >  
class ATL_NO_VTABLE IDBCreateCommandImpl   
   : public IDBCreateCommand  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Объект сеанса, производный от `IDBCreateCommandImpl`.  
  
 *CommandClass*  
 Класс команд.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[CreateCommand](#createcommand)|Создает новую команду.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительный интерфейс для объекта сеанса, чтобы получить новую команду.  

## <a name="createcommand"></a> IDBCreateCommandImpl::CreateCommand
Создает новую команду и возвращает запрошенный интерфейс.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IDBCreateCommand::CreateCommand](/previous-versions/windows/desktop/ms709772\(v=vs.85\)) в *справочнике программиста OLE DB*.  
  
 Некоторые параметры соответствуют *Справочник программиста OLE DB по* параметры разные имена, которые описаны в `IDBCreateCommand::CreateCommand`:  
  
|Параметры шаблона OLE DB|*Справочник программиста OLE DB по* параметров|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)