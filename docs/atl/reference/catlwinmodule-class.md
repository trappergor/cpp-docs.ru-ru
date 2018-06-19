---
title: Класс CAtlWinModule | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14b918747d9b7bee1b661eebd61fbb35325861e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358056"
---
# <a name="catlwinmodule-class"></a>Класс CAtlWinModule
Этот класс обеспечивает поддержку компоненты ATL управления окнами.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|Конструктор.|  
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Добавляет объект данных.|  
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Возвращает указатель на объект данных модуля окна.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс обеспечивает поддержку для всех классов ATL, которые требуются функции управления окнами.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)  
  
 `CAtlWinModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="addcreatewnddata"></a>  CAtlWinModule::AddCreateWndData  
 Этот метод инициализирует и добавляет `_AtlCreateWndData` структуры.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pData`  
 Указатель на `_AtlCreateWndData` структуры инициализируются и добавлен к текущему модулю.  
  
 `pObject`  
 Указатель на объект **это** указателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) какие инициализирует [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуры. Эта структура будет хранить **это** указатель, используемый для получения экземпляра класса в процедуры окна.  
  
##  <a name="catlwinmodule"></a>  CAtlWinModule::CAtlWinModule  
 Конструктор.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>Примечания  
 При сбое инициализации **EXCEPTION_NONCONTINUABLE** возникает исключение.  
  
##  <a name="dtor"></a>  CAtlWinModule:: ~ CAtlWinModule  
 Деструктор  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="extractcreatewnddata"></a>  CAtlWinModule::ExtractCreateWndData  
 Этот метод возвращает указатель на `_AtlCreateWndData` структуры.  
  
```
void* ExtractCreateWndData();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на `_AtlCreateWndData` структуры добавлены ранее с [CAtlWinModule::AddCreateWndData](#addcreatewnddata), или значение NULL, если объект не доступен.  
  
## <a name="see-also"></a>См. также  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)
