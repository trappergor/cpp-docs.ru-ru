---
title: "Класс CWndClassInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWndClassInfo
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
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f036d79c7a9420e083eb86023c5cbf98906cc1cc
ms.lasthandoff: 02/24/2017

---
# <a name="cwndclassinfo-class"></a>Класс CWndClassInfo
Этот класс предоставляет методы для регистрации сведений для класса окна.  
  
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
|[m_bSystemCursor](#m_bsystemcursor)|Определяет, ссылается ли курсор ресурсов системы курсора или курсора, содержащихся в ресурсе модуля.|  
|[m_lpszCursorID](#m_lpszcursorid)|Задает имя ресурса курсора.|  
|[m_lpszOrigName](#m_lpszorigname)|Содержит имя существующего класса окна.|  
|[m_szAutoName](#m_szautoname)|Содержит созданный ATL имя класса окна.|  
|[m_wc](#m_wc)|Хранит сведения о классе окна в **WNDCLASSEX** структуры.|  
|[pWndProc](#pwndproc)|Указывает на процедуру окна существующий класс окон.|  
  
## <a name="remarks"></a>Примечания  
 `CWndClassInfo`Управляет сведения класса окна. Как правило, используется `CWndClassInfo` посредством одного из трех макросы `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, или `DECLARE_WND_SUPERCLASS`, как описано в следующей таблице:  
  
|Макрос|Описание|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971)|`CWndClassInfo`Регистрирует сведения для нового класса окна.|  
|[DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411)|`CWndClassInfo`Регистрирует сведения для нового класса окна, включая параметры класса.|  
|[DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd)|`CWndClassInfo`Регистрирует сведения для класса окна, который основан на существующем классе, но использует другую процедуру окна. Этот прием называется создание суперклассов.|  
  
 По умолчанию [CWindowImpl](../../atl/reference/cwindowimpl-class.md) включает `DECLARE_WND_CLASS` макрос для создания окна на основании нового класса окна. DECLARE_WND_CLASS содержит стили по умолчанию и цвет фона для элемента управления. Если требуется задать стиль и цвет фона самостоятельно, необходимо создать собственный класс из `CWindowImpl` и включить `DECLARE_WND_CLASS_EX` макрос в определении класса.  
  
 Если вы хотите создать окно, в зависимости от имеющегося класса окон, необходимо создать собственный класс из `CWindowImpl` и включить `DECLARE_WND_SUPERCLASS` макрос в определении класса. Пример:  
  
 [!code-cpp[NVC_ATL_Windowing&#43;](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 Дополнительные сведения о классах окна в разделе [классы окон](http://msdn.microsoft.com/library/windows/desktop/ms632596) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="a-namematoma--cwndclassinfomatom"></a><a name="m_atom"></a>CWndClassInfo::m_atom  
 Содержит уникальный идентификатор класса зарегистрированного окна.  
  
```
ATOM m_atom;
```  
  
##  <a name="a-namembsystemcursora--cwndclassinfombsystemcursor"></a><a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor  
 Если **TRUE**, будут загружены системный ресурс курсора, если класс окна зарегистрирован.  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>Примечания  
 В противном случае — курсор ресурса, содержащегося в модуле будут загружены.  
  
 `CWndClassInfo`использует `m_bSystemCursor` только если [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) указан макрос. В этом случае `m_bSystemCursor` инициализируется **TRUE**. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="a-namemlpszcursorida--cwndclassinfomlpszcursorid"></a><a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID  
 Задает имя ресурса курсора или идентификатор ресурса в младшее слово и ноль в старшее слово.  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>Примечания  
 Если класс окна зарегистрирован, дескриптор курсора определяется `m_lpszCursorID` извлекается и хранятся в [m_wc](#m_wc).  
  
 `CWndClassInfo`использует `m_lpszCursorID` только если [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) указан макрос. В этом случае `m_lpszCursorID` инициализируется **IDC_ARROW**. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="a-namemlpszorignamea--cwndclassinfomlpszorigname"></a><a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName  
 Содержит имя существующего класса окна.  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>Примечания  
 `CWndClassInfo`использует `m_lpszOrigName` только при включении [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос в определении класса. В этом случае `CWndClassInfo` регистрирует класс окна на основе класса с именем, `m_lpszOrigName`. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="a-namemszautonamea--cwndclassinfomszautoname"></a><a name="m_szautoname"></a>CWndClassInfo::m_szAutoName  
 Содержит имя класса окна.  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>Примечания  
 `CWndClassInfo`использует `m_szAutoName` только тогда, когда **NULL** передается `WndClassName` параметр [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971), [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) или [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd). Если класс окна зарегистрирован ATL будет составить имя.  
  
##  <a name="a-namemwca--cwndclassinfomwc"></a><a name="m_wc"></a>CWndClassInfo::m_wc  
 Хранит сведения о классе окна в [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577) структуры.  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>Примечания  
 Если вы указали [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) макрос, `m_wc` содержит сведения о нового класса окна.  
  
 Если вы указали [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос, `m_wc` содержит сведения о суперклассе — класс окна, который основан на существующем классе, но использует другую процедуру окна. [m_lpszOrigName](#m_lpszorigname) и [pWndProc](#pwndproc) сохранить имя существующий класс окон и процедуре окна, соответственно.  
  
##  <a name="a-namepwndproca--cwndclassinfopwndproc"></a><a name="pwndproc"></a>CWndClassInfo::pWndProc  
 Указывает на процедуру окна существующий класс окон.  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>Примечания  
 `CWndClassInfo`использует `pWndProc` только при включении [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос в определении класса. В этом случае `CWndClassInfo` регистрирует класс окна, который основан на существующем классе, но использует другую процедуру окна. Процедура окна существующий класс окон сохраняются в `pWndProc`. Дополнительные сведения см. в разделе [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Обзор.  
  
##  <a name="a-nameregistera--cwndclassinforegister"></a><a name="register"></a>CWndClassInfo::Register  
 Вызывается методом [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create) зарегистрировать класс окна, если он не был зарегистрирован.  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>Параметры  
 `pProc`  
 [out] Указывает исходную процедуру окна существующего класса окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха atom, однозначно идентифицирующий класс окна регистрируется. В противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если вы указали [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (по умолчанию в [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) или [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) макрос, `Register` регистрирует новый класс окна. В этом случае `pProc` параметр не используется.  
  
 Если вы указали [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) макрос, `Register` регистрирует суперкласса — класс окна, который основан на существующем классе, но использует другую процедуру окна. Процедура окна существующий класс окон возвращается в `pProc`.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
