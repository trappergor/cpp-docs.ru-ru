---
title: Класс CNoMultipleResults | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CNoMultipleResults
- ATL.CNoMultipleResults
- ATL::CNoMultipleResults
dev_langs:
- C++
helpviewer_keywords:
- CNoMultipleResults class
ms.assetid: 343e77c4-b319-476e-b592-901ab9b2f34e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c2e588021b1600b1b3ac6e04f91ab07649755a2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096834"
---
# <a name="cnomultipleresults-class"></a>Класс CNoMultipleResults
Используется в качестве аргумента шаблона (*тип TMultiple*) для [CCommand](../../data/oledb/ccommand-class.md) для создания оптимизированного команды, который обрабатывает один результирующий набор.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CNoMultipleResults  
```  
  
## <a name="remarks"></a>Примечания  
 Команда для обработки нескольких результирующих наборов, используйте [CMultipleResults](../../data/oledb/cmultipleresults-class.md) вместо него.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)