---
title: "Класс CAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
dev_langs: C++
helpviewer_keywords: CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3f92d86ff67cc4ebfa752e84373c4f77bf3dc55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="caccessor-class"></a>Класс CAccessor
Представляет один из типов доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      template < class   
      T  
       >  
class CAccessor : public CAccessorBase, public T  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс записей пользователя.  
  
## <a name="remarks"></a>Примечания  
 Он используется, когда запись статически привязан к источнику данных. Запись содержит буфера. Этот класс поддерживает несколько методов доступа в наборе строк.  
  
 Используйте этот тип метода доступа, если известно, что структура и тип базы данных.  
  
 Если ваш метод доступа содержит поля, указывающие на памяти (такие как `BSTR` или интерфейса), должен быть освобожден, вызовите функцию-член [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) до следующего запись доступна для чтения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)