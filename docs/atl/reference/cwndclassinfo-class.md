---
title: "Класс CWndClassInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
dev_langs:
- C++
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
caps.latest.revision: 22
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
ms.openlocfilehash: 071a6683a459c1b668cfa3eb5e866b461d82ab29
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="cwndclassinfo-class"></a>Класс CWndClassInfo
Этот класс предоставляет методы для регистрации сведений о для класса окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CWndClassInfo
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|[Регистрация](#register)|Регистрирует класс окна.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_atom](#m_atom)|Уникально идентифицирует класс зарегистрированных окна.|  
|[m_bSystemCursor](#m_bsystemcursor)|Указывает, относится ли ресурса курсора системный курсор или курсор, содержащиеся в ресурсе модуля.|  
|[m_lpszCursorID](#m_lpszcursorid)|Задает имя ресурса курсора.|  
|[m_lpszOrigName](#m_lpszorigname)|Содержит имя существующего класса окна.|  
|[m_szAutoName](#m_szautoname)|Содержит создаваемого ATL имени класса окна.|  
|[m_wc](#m_wc)|Хранит сведения о классе окна в **WNDCLASSEX** структуры.|  
|[pWndProc](#pwndproc)|Указывает процедуру окна существующего класса окна.|  
  
## <a name="remarks"></a>Примечания  
 `CWndClassInfo`Управляет данными класса окна. Как правило, используется `CWndClassInfo` посредством одного из трех макросов `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, или `DECLARE_WND_SUPERCLASS`, как описано в следующей таблице:  
  
|Макрос|Описание|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`Регистрирует сведения для нового класса окна.|  
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`Регистрирует сведения для нового класса окна, включая параметры класса.|  
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`Регистрирует сведения для класса окна, который основан на существующем классе, но использует другую процедуру окна. Этот прием называется создание суперклассов.|  
  
 По умолчанию [CWindowImpl](../../atl/reference/cwindowimpl-class.md) включает `DECLARE_WND_CLASS` макрос для создания окна на основании нового класса окна. DECLARE_WND_CLASS предоставляет стили по умолчанию и цвет фона для элемента управления. Если требуется задать стиль и цвет фона самостоятельно вашей создайте класс, производный от `CWindowImpl` и включать `DECLARE_WND_CLASS_EX` макроса в определении класса.  
  
 Если вы хотите создать окно на основе существующего класса окна, получении класса из `CWindowImpl` и включать `DECLARE_WND_SUPERCLASS` макроса в определении класса. Например:  
  
 [!code-cpp[NVC_ATL_Windowing #43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 Дополнительные сведения о классах окна см. в разделе [классы окон](http://msdn.microsoft.com/library/windows/desktop/ms632596) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="m_atom"></a>CWndClassInfo::m_atom  
 Содержит уникальный идентификатор класса зарегистрированного окна.  
  
```
ATOM m_atom;
```  
  
##  <a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor  
 Если **TRUE**, курсор на системном ресурсе будут загружаться при регистрации класса окна.  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>Примечания  
 В противном случае курсор ресурсов, содержащихся в модуле будут загружены.  
  
 `CWndClassInfo`использует `m_bSystemCursor` только если [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) указан макрос. В этом случае `m_bSystemCursor` инициализируется **TRUE**. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID  
 Задает имя ресурса курсор или идентификатор ресурса в младшее слово и ноль в word высокого порядка.  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>Примечания  
 При регистрации класса окна, дескриптор курсора определяется `m_lpszCursorID` извлекается и хранятся в [m_wc](#m_wc).  
  
 `CWndClassInfo`использует `m_lpszCursorID` только если [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) указан макрос. В этом случае `m_lpszCursorID` инициализируется **IDC_ARROW**. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName  
 Содержит имя существующего класса окна.  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>Примечания  
 `CWndClassInfo`использует `m_lpszOrigName` только при включении [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макроса в определении класса. В этом случае `CWndClassInfo` регистрирует класс окна на основе класса с именем `m_lpszOrigName`. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="m_szautoname"></a>CWndClassInfo::m_szAutoName  
 Содержит имя класса окна.  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>Примечания  
 `CWndClassInfo`использует `m_szAutoName` только тогда, когда **NULL** передается `WndClassName` параметр [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) или [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass). ATL формируется имя при регистрации класса окна.  
  
##  <a name="m_wc"></a>CWndClassInfo::m_wc  
 Хранит сведения о классе окна в [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577) структуры.  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>Примечания  
 Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) макрос, `m_wc` содержит сведения о нового класса окна.  
  
 Если вы указали [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос, `m_wc` содержит сведения о суперклассе — класс окна, который основан на существующем классе, но использует другую процедуру окна. [m_lpszOrigName](#m_lpszorigname) и [pWndProc](#pwndproc) сохранить имя существующего класса окна и процедуру окна, соответственно.  
  
##  <a name="pwndproc"></a>CWndClassInfo::pWndProc  
 Указывает процедуру окна существующего класса окна.  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>Примечания  
 `CWndClassInfo`использует `pWndProc` только при включении [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макроса в определении класса. В этом случае `CWndClassInfo` регистрирует класс окна, который основан на существующем классе, но использует другую процедуру окна. Оконная функция существующий класс окна сохраняется в `pWndProc`. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="register"></a>CWndClassInfo::Register  
 Вызывается методом [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create) зарегистрировать класс окна, если он не был зарегистрирован.  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>Параметры  
 `pProc`  
 [out] Указывает исходную процедуру окна существующего класса окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения atom, однозначно определяющий регистрируемый класс окна. В противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если вы указали [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) макрос, `Register` регистрирует новый класс окна. В этом случае `pProc` параметр не используется.  
  
 Если вы указали [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) макрос, `Register` регистрирует суперкласса — класс окна, который основан на существующем классе, но использует другую процедуру окна. Оконная функция существующий класс окна возвращается в `pProc`.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
