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
ms.openlocfilehash: 6d68daae7bce6ca4c9ffafe7a24c80cff3a5426a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059861"
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