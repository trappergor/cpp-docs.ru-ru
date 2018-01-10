---
title: "CHAIN_PROPERTY_SET | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CHAIN_PROPERTY_SET
dev_langs: C++
helpviewer_keywords: CHAIN_PROPERTY_SET macro
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1de482b285f24ce9ed68bd70fa7b21b0b66a4d56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="chainpropertyset"></a>CHAIN_PROPERTY_SET
Этот макрос объединяются в цепочку группы свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
CHAIN_PROPERTY_SET(  
ChainClass   
)  
  
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