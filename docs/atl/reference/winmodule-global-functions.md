---
title: "Глобальные функции WinModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
dev_langs: C++
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 290566c27fa5698c4a00a323a8c2431681b69d88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="winmodule-global-functions"></a>Глобальные функции WinModule
Эти функции обеспечивают поддержку `_AtlCreateWndData` структуры операций.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  `            
##  <a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData  
 Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.  
   
```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pWinModule`  
 Указатель на модуль [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) структуры.  
  
 `pData`  
 Указатель на [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуры инициализируются и добавлен к текущему модулю.  
  
 `pObject`  
 Указатель на объект **это** указателя.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `_AtlCreateWndData` структуру, которая используется для хранения **это** указатель используется для ссылки на экземпляры класса и добавляет его в список, который ссылается на модуль `_ATL_WIN_MODULE70` структуры. Вызывается методом [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).  
  
##  <a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData  
 Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.  
 
```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```  
  
### <a name="parameters"></a>Параметры  
 `pWinModule`  
 Указатель на модуль [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция будет извлечения существующей `_AtlCreateWndData` структуру из списка ссылается модуль `_ATL_WIN_MODULE70` структуры.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
