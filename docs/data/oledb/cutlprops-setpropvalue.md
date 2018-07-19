---
title: CUtlProps::SetPropValue | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs:
- C++
helpviewer_keywords:
- SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 73f2432a23adf8fe11f759c2caa85d9653040635
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099073"
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
Задает свойство в наборе свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pguidPropSet`  
 [in] Идентификатор GUID набор свойств.  
  
 `dwPropId`  
 [in] Индекс свойства.  
  
 `pvValue`  
 [in] Указатель на значение variant, который содержит новое значение свойства.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `Failure` в случае ошибки и `S_OK` в случае успешного выполнения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)