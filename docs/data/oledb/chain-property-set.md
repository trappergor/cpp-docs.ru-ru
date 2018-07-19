---
title: CHAIN_PROPERTY_SET | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CHAIN_PROPERTY_SET
dev_langs:
- C++
helpviewer_keywords:
- CHAIN_PROPERTY_SET macro
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9db57535f3f0bc7653c80b83c3e0115727eed707
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094339"
---
# <a name="chainpropertyset"></a>CHAIN_PROPERTY_SET
Этот макрос объединяются в цепочку группы свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
CHAIN_PROPERTY_SET(ChainClass)  
  
```  
  
#### <a name="parameters"></a>Параметры  
 *ChainClass*  
 [in] Имя класса, чтобы свойства цепочки. Это класс, созданный программой мастер проектов ATL, которая уже содержит схему (например, сеанса, команды или данных источника объекта класса).  
  
## <a name="remarks"></a>Примечания  
 Можно прикреплять набор свойств из другого класса свой собственный класс, а затем доступа к свойствам непосредственно из класса.  
  
> [!CAUTION]
>  Используйте этот макрос только в случае необходимости. Неправильное использование может привести к объекту-получателю ошибкой проверка на совместимость с OLE DB.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)