---
title: "Точка подключения глобальные функции | Документы Microsoft"
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
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
caps.latest.revision: 20
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
ms.openlocfilehash: 8271f512141e4d2cc274d180b31e1ad33bfc354e
ms.lasthandoff: 02/24/2017

---
# <a name="connection-point-global-functions"></a>Точка подключения глобальные функции
Эти функции обеспечивают поддержку точки подключения и приемник карт.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|Создает связь между точкой подключения объекта и приемником клиента.|  
|[AtlUnadvise](#atlunadvise)|Завершает подключение, установленное через `AtlAdvise`.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|Содержания или unadvises записей в картой приемника событий.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
   
##  <a name="a-nameatladvisea--atladvise"></a><a name="atladvise"></a>AtlAdvise  
 Создает связь между точкой подключения объекта и приемником клиента.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkCP`  
 [in] Указатель на **IUnknown** объекта клиент хочет подключиться с.  
  
 *pUnk*  
 [in] Указатель на клиент **IUnknown**.  
  
 `iid`  
 [in] Идентификатор GUID точки подключения. Как правило это то же самое исходящего интерфейса, управляемого с использованием точки подключения.  
  
 `pdw`  
 [out] Указатель на файл cookie, который уникально идентифицирует соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Приемник реализует исходящего интерфейса, поддерживаемого точкой подключения. Клиент использует `pdw` файл cookie, удалите подключение, передав его в [AtlUnadvise](#atlunadvise).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#91;](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="a-nameatlunadvisea--atlunadvise"></a><a name="atlunadvise"></a>AtlUnadvise  
 Завершает подключение, установленное с помощью [AtlAdvise](#atladvise).  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkCP`  
 [in] Указатель на **IUnknown** объекта, связанный с клиентом.  
  
 `iid`  
 [in] Идентификатор GUID точки подключения. Как правило это то же самое исходящего интерфейса, управляемого с использованием точки подключения.  
  
 `dw`  
 [in] Файл cookie, который уникально идентифицирует соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#96;](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="a-nameatladvisesinkmapa--atladvisesinkmap"></a><a name="atladvisesinkmap"></a>AtlAdviseSinkMap  
 Вызывайте эту функцию для соединения или разъединения всех записей в схеме событий приемника объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 [in] Указатель на объект, содержащий приемником сопоставления.  
  
 `bAdvise`  
 [in] **true** знать, если все записи приемника **false** Если все операции приемника должны быть unadvised.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#92;](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы точки подключения](../../atl/reference/connection-point-macros.md)

