---
title: "Класс IRowsetImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetImpl
dev_langs: C++
helpviewer_keywords: IRowsetImpl class
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c934ce36ae20727340ea9d2e6bd4d95272c908f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimpl-class"></a>Класс IRowsetImpl
Предоставляет реализацию интерфейса `IRowset`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*   
   >  
>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetImpl`.  
  
 `RowsetInterface`  
 Класс, производный от `IRowsetImpl`.  
  
 `RowClass`  
 Устройство хранения для **HROW**.  
  
 `MapClass`  
 Устройство хранения для все дескрипторы строк, удерживаемые поставщика.  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|Добавляет счетчик ссылок в дескриптор существующей строки.|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|Вызывается методом [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) выделить новый **HROW**. Не вызывается непосредственно пользователем.|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|Извлекает данные из копии строки в наборе строк.|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|Возвращает состояние для указанного поля.|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|Последовательно извлекает строки запоминание предыдущей позиции.|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|Конструктор. Не вызывается непосредственно пользователем.|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|Вызывается методом [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md). Не вызывается непосредственно пользователем.|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|Освобождает строк.|  
|[Свойство RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)|Перемещает позицию следующей выборки в его начальное положение; то есть создать его положение при первоначальной набора строк.|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|Задает флаги состояния для указанного поля.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|Указывает, поддерживает ли поставщик обратной выборка.|  
|[m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|Указывает ли поставщик может его прокрутки курсора вперед.|  
|[m_bReset](../../data/oledb/irowsetimpl-m-breset.md)|Указывает, ли поставщик сбросить его положение курсора. Это имеет особое значение при прокрутки вперед или назад в выборке [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|  
|[m_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|Индекс для строк, представляющий курсор.|  
|[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|Список дескрипторов строк.|  
  
## <a name="remarks"></a>Примечания  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) имеет базовый интерфейс набора строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)