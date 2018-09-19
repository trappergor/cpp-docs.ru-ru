---
title: Класс CNoMultipleResults | Документация Майкрософт
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
ms.openlocfilehash: 67658f6edadd7723789288ab268b97cecdd611d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017360"
---
# <a name="cnomultipleresults-class"></a>Класс CNoMultipleResults

Используется в качестве аргумента шаблона (*тип TMultiple*) для [CCommand](../../data/oledb/ccommand-class.md) Создание оптимизированного команды, который обрабатывает один результат набора.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CNoMultipleResults  
```  
  
## <a name="remarks"></a>Примечания  

Команды для обработки нескольких результирующих наборов, используйте [CMultipleResults](../../data/oledb/cmultipleresults-class.md) вместо этого.  
  
## <a name="requirements"></a>Требования  

**Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)