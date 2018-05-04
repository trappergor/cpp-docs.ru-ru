---
title: Глобальные функции COM-карты | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 509479a923203acd80eaac1ef90aa64125d208c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="com-map-global-functions"></a>Глобальные функции COM карты
Эти функции обеспечивают поддержку для сопоставления COM **IUnknown** реализации.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Делегирует **IUnknown** неагрегированные объекта.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Создает эффективный код для сравнения интерфейсы с параметром **IUnknown**.|  

  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface  
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
 [!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown  
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
