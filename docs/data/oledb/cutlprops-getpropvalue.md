---
title: "CUtlProps::GetPropValue | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs: C++
helpviewer_keywords: GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f6af9c8d909039927a7b4ad1f4840adac4353c97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
Возвращает свойство из набора свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      OUT_OF_LINE HRESULT GetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pguidPropSet`  
 [in] Идентификатор GUID набор свойств.  
  
 `dwPropId`  
 [in] Индекс свойства.  
  
 `pvValue`  
 [out] Указатель на значение variant, который содержит новое значение свойства.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `Failure`в случае ошибки и `S_OK` в случае успешного выполнения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)