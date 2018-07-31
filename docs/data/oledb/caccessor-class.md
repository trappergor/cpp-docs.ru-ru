---
title: Класс CAccessor | Документация Майкрософт
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
ms.openlocfilehash: 9e7f722d4d1759bdec7a23bb15076b38de000eb6
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337421"
---
# <a name="caccessor-class"></a>Класс CAccessor
Представляет один из типов доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
template <class T>  
class CAccessor : public CAccessorBase, public T  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс записей пользователя.  
  
## <a name="remarks"></a>Примечания  
 Он используется, когда запись статически привязан к источнику данных. Запись содержит буфера. Этот класс поддерживает несколько методов доступа в наборе строк.  
  
 Используйте этот тип метода доступа, если вы знаете структуру и тип базы данных.  
  
 Если ваш метод доступа содержит поля, указывающие на область памяти (такие как `BSTR` или интерфейс), должен быть освобожден, вызовите функцию-член [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) до следующей запись доступна для чтения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)