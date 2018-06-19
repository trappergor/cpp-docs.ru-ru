---
title: CRowsetImpl::GetColumnInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a989b31d672c9019d2ed5e61490f4e0042ab4c47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096471"
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