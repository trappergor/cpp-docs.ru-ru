---
title: "Класс CCommand | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
dev_langs:
- C++
helpviewer_keywords:
- CCommand class
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4c53d7b27c98e0509cd434bf6eac2412b9c1a1a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ccommand-class"></a>Класс CCommand
Предоставляет методы для установки и выполнить команду.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor,  
          template <typename T> class TRowset = CRowset,  
          class TMultiple = CNoMultipleResults>  
class CCommand :   
           public CAccessorRowset <TAccessor, TRowset>,  
           public CCommandBase,  
           public TMultiple  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Тип класса метода доступа (такие как `CDynamicParameterAccessor`, `CDynamicStringAccessor`, или `CEnumeratorAccessor`), необходимо, чтобы использовался. Значение по умолчанию — `CNoAccessor`, который указывает, что класс не поддерживает параметры или выходные столбцы.  
  
 `TRowset`  
 Тип класса набора строк (таких как `CArrayRowset` или `CNoRowset`), необходимо, чтобы использовался. Значение по умолчанию — `CRowset`.  
  
 `TMultiple`  
 Чтобы использовать команду OLE DB, которая может вернуть несколько результатов, укажите [CMultipleResults](../../data/oledb/cmultipleresults-class.md). В противном случае используйте [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Дополнительные сведения см. в разделе [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx).  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Закрыть](../../data/oledb/ccommand-close.md)|Закрывает текущую команду.|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|Извлекает следующий результат, когда использование нескольких результирующих наборов.|  
|[Открыть](../../data/oledb/ccommand-open.md)|Выполняет и при необходимости привязывает команды.|  
  
### <a name="inherited-methods"></a>Унаследованные методы  
  
|||  
|-|-|  
|[Create](../../data/oledb/ccommand-create.md)|Создание новой команды для указанного сеанса, а затем задает текст команды.|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|Создание новой команды.|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|Возвращает список параметров команды, их имена и их типы.|  
|[Подготовка](../../data/oledb/ccommand-prepare.md)|Проверяет и оптимизирует текущую команду.|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|Освобождает параметрическим при необходимости, а затем освобождает команды.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|Задает собственный тип каждого параметра команды.|  
|[Аннулирующие](../../data/oledb/ccommand-unprepare.md)|Отменяет план выполнения текущей команды.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется, когда требуется выполнить операцию на основе параметров или для выполнения команды. Если необходимо просто открыть простого набора строк, используйте [CTable](../../data/oledb/ctable-class.md) вместо него.  
  
 Класс доступа, которую вы используете определяет метод привязки параметров и данных.  
  
 Обратите внимание, что нельзя использовать хранимые процедуры с поставщиком OLE DB для Jet, поскольку этот поставщик не поддерживает хранимые процедуры, (только константы допускаются в строках запроса).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)