---
title: "CUtlProps::OnPropertyChanged | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
dev_langs:
- C++
helpviewer_keywords:
- OnPropertyChanged method
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f87f6842f33bd58be9cde515396f495402235a77
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cutlpropsonpropertychanged"></a>CUtlProps::OnPropertyChanged
Вызывается после задания свойства для обработки связанных свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>Параметры  
 `iCurSet`  
 Индекс в массиве набор свойств. нуль, если определено только одно свойство.  
  
 `pDBProp`  
 Идентификатор свойства и новое значение в [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) структуры.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`. Значение по умолчанию возвращаемое значение — `S_OK`.  
  
## <a name="remarks"></a>Примечания  
 Если необходимо обработать связанные свойства, такие как закладки и обновления, значения которых зависят от значения другого свойства, необходимо переопределить эту функцию.  
  
## <a name="example"></a>Пример  
 В этой функции пользователь получает идентификатор свойства из `DBPROP*` параметра. Теперь можно сравнить идентификатор для свойства в цепочке. Если свойство найдено, `SetProperties` вызывается со свойством, которое будет установлено вместе с другим свойством. В этом случае, если вы получаете `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, или `DBPROP_ORDEREDBOOKMARKS` свойства, одно значение `DBPROP_BOOKMARKS` свойства.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)