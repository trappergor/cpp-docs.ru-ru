---
title: Класс CManualAccessor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7b8efc46971b1aa72f8c5e572aa540bfed250d2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098177"
---
# <a name="cmanualaccessor-class"></a>Класс CManualAccessor
Представляет тип метода доступа, предназначенных для расширенного использования.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CManualAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|Добавляет запись привязки выходных столбцов.|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|Добавление параметра записи для доступа к параметру.|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Выделяет память для параметра bind структуры и инициализирует параметризованные члены данных.|  
  
## <a name="remarks"></a>Примечания  
 С помощью `CManualAccessor`, можно указать параметр и вывода привязки столбцов вызовом функции времени выполнения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [DBViewer](../../visual-cpp-samples.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-класс](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)