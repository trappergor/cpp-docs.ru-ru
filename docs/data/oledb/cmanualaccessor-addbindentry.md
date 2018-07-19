---
title: CManualAccessor::AddBindEntry | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59793bd61b17fe2ead4948932efa1b583da8e1a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098058"
---
# <a name="cmanualaccessoraddbindentry"></a>CManualAccessor::AddBindEntry
Добавляет запись привязки выходных столбцов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *справочника программиста OLE DB*.  
  
 `nOrdinal`  
 [in] Номер столбца.  
  
 `wType`  
 [in] Тип данных.  
  
 `nColumnSize`  
 [in] Размер столбца в байтах.  
  
 `pData`  
 [in] Указатель на данные столбцов, сохраненного в буфере.  
  
 `pLength`  
 [in] Указатель длины поля, если это необходимо.  
  
 `pStatus`  
 [in] Указатель на переменную может быть привязано к столбцу "состояние", при необходимости.  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать эту функцию, необходимо сначала вызвать [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Не удается добавить записей больше, чем количество столбцов, указанных в `CreateAccessor`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [Образец DBViewer](../../visual-cpp-samples.md)