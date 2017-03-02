---
title: "Класс CAtlWinModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlWinModule
- ATL.CAtlWinModule
- CAtlWinModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6db3ae9e610605524683e984f2aba602b1daf0d4
ms.lasthandoff: 02/24/2017

---
# <a name="catlwinmodule-class"></a>Класс CAtlWinModule
Этот класс обеспечивает поддержку для работы с окнами компонентов ATL.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>Члены  
  
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
  
##  <a name="a-nameaddcreatewnddataa--catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData  
 Этот метод инициализирует и добавляет `_AtlCreateWndData` структуры.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pData`  
 Указатель на `_AtlCreateWndData` структуры для инициализации и добавления в текущем модуле.  
  
 `pObject`  
 Указатель на объект **это** указателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [AtlWinModuleAddCreateWndData](http://msdn.microsoft.com/library/8463a6ed-07ea-4aad-92ec-ded681601b32) какие инициализирует [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) структуры. Эта структура будет хранить **это** указателем, используется для получения экземпляра класса в процедуры окна.  
  
##  <a name="a-namecatlwinmodulea--catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule  
 Конструктор.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>Примечания  
 В случае сбоя инициализации **EXCEPTION_NONCONTINUABLE** возникает исключение.  
  
##  <a name="a-namedtora--catlwinmodulecatlwinmodule"></a><a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule  
 Деструктор  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="a-nameextractcreatewnddataa--catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData  
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

