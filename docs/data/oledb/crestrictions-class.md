---
title: Класс CRestrictions | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b0b174a8e53f72b0077d10fd1728c4e726e0f218
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098489"
---
# <a name="crestrictions-class"></a>Класс CRestrictions
Универсальный класс, позволяющий указать ограничения для наборов строк схемы.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, short nRestrictions, const GUID* pguid>  
class CRestrictions : 
        public CSchemaRowset <T, nRestrictions>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, используемый для метода доступа.  
  
 `nRestrictions`  
 Число столбцов ограничений для набора строк схемы.  
  
 `pguid`  
 Указатель на идентификатор GUID для схемы.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Открыть](../../data/oledb/crestrictions-open.md)|Возвращает результирующий набор, в соответствии с ограничения, предоставленное пользователем.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)