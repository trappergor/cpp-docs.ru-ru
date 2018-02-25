---
title: "CRowsetImpl::GetColumnInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18ed527d47b8bfb4ffa64c88597cc2e241ad9852
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplgetcolumninfo"></a>CRowsetImpl::GetColumnInfo
Извлекает сведения о столбце для конкретного клиентского запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,  
   ULONG* pcCols);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pv`  
 [in] Указатель на пользователя `CRowsetImpl` производного класса.  
  
 `pcCols`  
 [in] Указатель (output), в число возвращаемых столбцов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на статическую **ATLCOLUMNINFO** структуры.  
  
## <a name="remarks"></a>Примечания  
 Этот метод является Дополнительно переопределения.  
  
 Этот метод вызывается методом несколько классов базовую реализацию, чтобы получить сведения о столбцах для конкретного клиентского запроса. Как правило, этот метод будет вызываться `IColumnsInfoImpl`. При переопределении этого метода необходимо поместить версия метода в вашей `CRowsetImpl`-производного класса. Так как метод может размещаться в классе без создания шаблона, необходимо изменить `pv` к соответствующему `CRowsetImpl`-производного класса.  
  
 В следующем примере демонстрируется **GetColumnInfo** использования. В этом примере **CMyRowset** — `CRowsetImpl`-производного класса. Чтобы переопределить `GetColumnInfo` для всех экземпляров этого класса, поместите следующий метод в **CMyRowset** определения класса:  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)