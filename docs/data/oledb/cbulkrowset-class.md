---
title: "Класс CBulkRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
dev_langs:
- C++
helpviewer_keywords:
- CBulkRowset class
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 288599a85cc63c59bf8b1bd013e197908adc9cc8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cbulkrowset-class"></a>Класс CBulkRowset
Извлекает и управляет строк для работы с данными в пакетном режиме путем получения нескольких дескрипторов строк с помощью одного вызова.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Класса метода доступа.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|Увеличивает счетчик ссылок.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|Конструктор.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|Извлекает первую строку данных, выполнения новых массовой выборки при необходимости.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|Переход к последней строке.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|Извлекает следующую строку данных.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|Переход к предыдущей строке.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|Получает строку, помеченную закладкой или строки с указанным смещением из эту закладку.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|Извлекает строки, начиная с долей позиции в наборе строк.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|Задает текущую строку (**m_nCurrentRow**) до нуля и выпусках все строки.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|Задает число дескрипторов строк извлечение одного вызова.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование `CBulkRowset` класса.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)