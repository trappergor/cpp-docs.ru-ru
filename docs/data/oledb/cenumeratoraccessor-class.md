---
title: "Класс CEnumeratorAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57595cb2440aa8ad83c7cc0ad6916b3f22d6fb37
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cenumeratoraccessor-class"></a>Класс CEnumeratorAccessor
Используемые [CEnumerator](../../data/oledb/cenumerator-class.md) доступ к данным из перечислитель набора строк.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CEnumeratorAccessor  
```  
  
## <a name="members"></a>Участники  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|Переменная, показывающего, является Перечислитель перечислитель родительский, если строка находится перечислитель.|  
|[m_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|Переменная, позволяющее определить, описывает ли строка источника данных или перечислителя.|  
|[m_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|Описание источника данных или перечислителя.|  
|[m_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|Имя источника данных или перечислителя.|  
|[m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|Строка для [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) для получения моникера для источника данных или перечислителя.|  
  
## <a name="remarks"></a>Примечания  
 Этот набор строк состоит из источников данных и перечислителей, видимый из текущего перечислителя.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)