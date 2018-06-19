---
title: Глобальные функции для точки подключения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dc6cd11cb1f04ba877524cd1ae6134a7dd93d09
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362795"
---
# <a name="connection-point-global-functions"></a>Глобальные функции для точки подключения
Эти функции обеспечивают поддержку для точки подключения и приемника карты.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|Создает связь между точкой подключения объекта и приемником клиента.|  
|[AtlUnadvise](#atlunadvise)|Завершает подключение, установленное с помощью `AtlAdvise`.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|Будет указано, или unadvises записей в схеме событий приемника.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
   
##  <a name="atladvise"></a>  AtlAdvise  
 Создает связь между точкой подключения объекта и приемником клиента.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
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
 [in] Идентификатор GUID точки подключения. Как правило это то же самое исходящего интерфейса, управляемого с помощью точки подключения.  
  
 `pdw`  
 [out] Указатель на файл cookie, однозначно определяющее соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Приемник реализует исходящего интерфейса, поддерживаемого точкой подключения. Клиент использует `pdw` куки-файл для удаления соединения путем ее передачи [AtlUnadvise](#atlunadvise).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>  AtlUnadvise  
 Завершает подключение, установленное с помощью [AtlAdvise](#atladvise).  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
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
 [in] Идентификатор GUID точки подключения. Как правило это то же самое исходящего интерфейса, управляемого с помощью точки подключения.  
  
 `dw`  
 [in] Файл cookie, однозначно определяющее соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>  AtlAdviseSinkMap  
 Вызывайте эту функцию для соединения или разъединения всех записей в схеме событий приемника объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 [in] Указатель на объект, содержащий приемником сопоставления.  
  
 `bAdvise`  
 [in] **true** Если все записи приемника должны быть проигнорирована; **false** Если все операции приемников должны быть unadvised.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы для работы с точками подключения](../../atl/reference/connection-point-macros.md)
