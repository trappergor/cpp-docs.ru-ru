---
title: Класс CAccessor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
dev_langs:
- C++
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dffefb74faf6836b9f2fc81a7800dc34084657cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="caccessor-class"></a>Класс CAccessor
Представляет один из типов доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
template <class T>  
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