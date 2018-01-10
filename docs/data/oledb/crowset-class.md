---
title: "Класс CRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>
- CRowset
- ATL::CRowset
- ATL::CRowset<TAccessor>
- ATL.CRowset
dev_langs: C++
helpviewer_keywords: CRowset class
ms.assetid: b0228a90-b8dd-47cc-b397-8d4c15c1e7f4
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b0d46ac3164f7f609e8a8a8099d500d04d91bf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowset-class"></a>Класс CRowset
Инкапсулирует объект набора строк OLE DB, а также несколько связанных интерфейсов и предоставляет методы обработки для набора строк данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class TAccessor = CAccessorBase>  
class CRowset  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Класса метода доступа. Значение по умолчанию — `CAccessorBase`.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/crowset-addrefrows.md)|Увеличивает счетчик ссылок, связанных с текущей строки.|  
|[Закрыть](../../data/oledb/crowset-close.md)|Освобождает строки и текущего `IRowset` интерфейса.|  
|[Compare](../../data/oledb/crowset-compare.md)|Сравнивает два закладки с помощью [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).|  
|[CRowset](../../data/oledb/crowset-crowset.md)|Создает новый `CRowset` объекта и (необязательно) связывает его с **IRowset** интерфейса, переданного в качестве параметра.|  
|[Удалить](../../data/oledb/crowset-delete.md)|Удаляет строки из набора строк с помощью [IRowsetChange:DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx).|  
|[FindNextRow](../../data/oledb/crowset-findnextrow.md)|Находит сопоставления следующую строку после указанной закладки.|  
|[GetApproximatePosition](../../data/oledb/crowset-getapproximateposition.md)|Возвращает приблизительное позицию строка, соответствующая закладки.|  
|[GetData](../../data/oledb/crowset-getdata.md)|Извлекает данные из копии строки в наборе строк.|  
|[GetDataHere](../../data/oledb/crowset-getdatahere.md)|Извлекает данные из указанного буфера.|  
|[GetOriginalData](../../data/oledb/crowset-getoriginaldata.md)|Получает данные недавно извлечены из либо передана в источник данных, игнорируя ожидающих изменений.|  
|[GetRowStatus](../../data/oledb/crowset-getrowstatus.md)|Возвращает состояние всех строк.|  
|[Вставить](../../data/oledb/crowset-insert.md)|Создает и вставляет новую строку, используя [IRowsetChange:InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx).|  
|[IsSameRow](../../data/oledb/crowset-issamerow.md)|Сравнивает указанной строки с текущей строкой.|  
|[MoveFirst](../../data/oledb/crowset-movefirst.md)|Перемещает расположение next fetch в исходное положение.|  
|[MoveLast](../../data/oledb/crowset-movelast.md)|Переходит на последнюю запись.|  
|[MoveNext](../../data/oledb/crowset-movenext.md)|Загружает данные из последовательного следующую строку или указанное число позиций после следующей строки.|  
|[MovePrev](../../data/oledb/crowset-moveprev.md)|Переход к предыдущей записи.|  
|[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)|Получает строку, помеченную закладкой или строки с указанным смещением из эту закладку.|  
|[MoveToRatio](../../data/oledb/crowset-movetoratio.md)|Извлекает строки, начиная с долей позиции в наборе строк.|  
|[ReleaseRows](../../data/oledb/crowset-releaserows.md)|Вызовы [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) для освобождения дескриптора текущей строки.|  
|[SetData](../../data/oledb/crowset-setdata.md)|Задает значения данных в один или несколько столбцов из строки с помощью [IRowsetChange:SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx).|  
|[Отменить](../../data/oledb/crowset-undo.md)|Отменяет все изменения, внесенные в строку с момента последней выборки или [обновление](../../data/oledb/crowset-update.md).|  
|[Обновление](../../data/oledb/crowset-update.md)|Передает все ожидающие изменения, внесенные в текущую строку с момента последней выборки или обновления.|  
|[UpdateAll](../../data/oledb/crowset-updateall.md)|Передает все ожидающие изменения, внесенные во все строки с момента последней выборки или обновления.|  
  
## <a name="remarks"></a>Примечания  
 В OLE DB набор строк — это объект, по которому программа задает и получает данные.  
  
 Этот класс не предназначен для создания экземпляра, но вместо этого передается в качестве параметра шаблона для `CTable` или `CCommand` (`CRowset` значение по умолчанию).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Образец DBViewer](../../visual-cpp-samples.md)   
 [Образец MultiRead](../../visual-cpp-samples.md)   
 [Образец атрибутов multiRead](../../visual-cpp-samples.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)