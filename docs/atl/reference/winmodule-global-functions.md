---
title: "Глобальные функции WinModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c477f4500bd4fe78f21f04c58b02d1b493f72c01
ms.lasthandoff: 02/24/2017

---
# <a name="winmodule-global-functions"></a>Глобальные функции WinModule
Эти функции обеспечивают поддержку `_AtlCreateWndData` структуры операций.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Эта функция используется для инициализации и добавления структуры `_AtlCreateWndData`.|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Вызывайте эту функцию для извлечения существующей структуры `_AtlCreateWndData`.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  `            
##  <a name="a-nameatlwinmoduleaddcreatewnddataa--atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData  
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
 Указатель на [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуры для инициализации и добавления в текущем модуле.  
  
 `pObject`  
 Указатель на объект **это** указателя.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `_AtlCreateWndData` структуру, которая используется для хранения **это** указатель используется для обращения к экземплярам класса и добавляет его в список, указанный для модуля `_ATL_WIN_MODULE70` структуры. Вызывается методом [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).  
  
##  <a name="a-nameatlwinmoduleextractcreatewnddataa--atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData  
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

