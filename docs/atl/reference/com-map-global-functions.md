---
title: "Глобальные функции COM-карты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: d6f23de1a5fd13d61d376acded35f9217d0a898d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="com-map-global-functions"></a>Глобальные функции COM карты
Эти функции обеспечивают поддержку для сопоставления COM **IUnknown** реализации.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Делегирует **IUnknown** неагрегированные объекта.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Создает эффективный код для сравнения интерфейсы с параметром **IUnknown**.|  

  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pThis`  
 [in] Указатель на объект, содержащий схему COM интерфейсы, предоставляемые в `QueryInterface`.  
  
 `pEntries`  
 [in] Массив **_ATL_INTMAP_ENTRY** структур, которые обращаются к карте доступные интерфейсы.  
  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, указанного в `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `AtlInternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если объект является статистическим выражением, `AtlInternalQueryInterface` не делегировать внешняя Неизвестная строка. Вы можете ввести интерфейсы в таблицу сопоставлений COM с помощью макроса [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одного из его вариантов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing #94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown  
 Вызывайте эту функцию для особого случая тестирования для **IUnknown**.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>Параметры  
 *rguid1*  
 [in] Идентификатор GUID для сравнения **IID_IUnknown**.  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы сопоставления COM](../../atl/reference/com-map-macros.md)

