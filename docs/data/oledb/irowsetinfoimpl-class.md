---
title: Класс IRowsetInfoImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetInfoImpl class
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f9b784dbb13ff39be21ccd353d514dd244d5ae41
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106223"
---
# <a name="irowsetinfoimpl-class"></a>Класс IRowsetInfoImpl
Предоставляет реализацию для [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetInfoImpl`.  
  
 `PropClass`  
 Класс определяемые пользователем свойства, значение по умолчанию `T`.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)|Возвращает текущие значения всех свойств, поддерживаемое набором строк.|  
|[GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|Возвращает указатель на интерфейс для набора строк, к которому применяется закладки.|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|Возвращает указатель интерфейса на объект (команды или сеанса), создавшего этот набор строк.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс для наборов строк. Этот класс реализует свойства набора строк с помощью [сопоставление набора свойств](../../data/oledb/begin-propset-map.md) определенные в классе команд. Несмотря на то, что класс строк отображается для класса команды свойство задает, набор строк прилагается свою собственную копию свойства времени выполнения при его создании с помощью объекта команды или сеанса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** altdb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)