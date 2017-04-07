---
title: "CReBar-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- rebar controls, control bar
- CReBar class
- Internet Explorer 4.0 common controls
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 38ac4611503bec70ea9f809a4d4f9d4b5133e30e
ms.lasthandoff: 02/24/2017

---
# <a name="crebar-class"></a>CReBar-класс
Панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления главной панели.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CReBar : public CControlBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReBar::AddBar](#addbar)|Добавляет диапазон главной панели.|  
|[CReBar::Create](#create)|Создает элемент управления главной панели и присоединяет его к `CReBar` объекта.|  
|[CReBar::GetReBarCtrl](#getrebarctrl)|Предоставляет прямой доступ к базовой стандартного элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 На главной панели объект может содержать множество дочерних окон, обычно других элементов управления, включая поля ввода, панели инструментов и списки. Объект главной панели можно отобразить его дочерних окон на указанном точечном рисунке. Приложения можно автоматически изменить размеры главной панели, или пользователь вручную изменять размеры главной панели, щелкните и перетащите его захвата.  
  
 ![Пример меню rebarmenu](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Элемент управления главной панели  
 На главной панели объект ведет себя аналогично объект панели инструментов. Главная панель использует механизм щелкните и перетащите для изменения размеров его делений. Контейнер элементов управления может содержать один или несколько полосы с каждого диапазона с любым сочетанием полосу захвата, точечный рисунок, текстовую метку и дочернего окна. Однако полосы не может содержать более одного дочернего окна.  
  
 **CReBar** использует [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) класса для обеспечения его реализации. Можно получить доступ к главной панели управления через [GetReBarCtrl](#getrebarctrl) преимуществами возможностей настройки элемента управления. Дополнительные сведения об элементах управления главной панели см. в разделе `CReBarCtrl`. Дополнительные сведения об использовании элементов управления главной панели см. в разделе [CReBarCtrl с помощью](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  Панель закрепления элементов управления MFC не поддерживают главной панели и объекты управления главной панели. Если **CRebar::EnableDocking** вызывается, приложение будет assert.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="addbar"></a>CReBar::AddBar  
 Вызовите эту функцию-член добавляемый диапазон на главной панели.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

 
BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Параметры  
 `pBar`  
 Указатель на `CWnd` объект, который представляет дочернее окно должны быть вставлены в главной панели. Указанный объект должен иметь **WS_CHILD**.  
  
 `lpszText`  
 Указатель на строку, содержащую текст, отображаемый на главной панели. **Значение NULL,** по умолчанию. Текст, содержащийся в `lpszText` не является частью дочернего окна; он находится на главной панели, сам.  
  
 `pbmp`  
 Указатель на `CBitmap` объект отображался на фоне главной панели. **Значение NULL,** по умолчанию.  
  
 `dwStyle`  
 A `DWORD` содержащий стиль, применяемый к главной панели. В разделе **fStyle** функции описание структуры Win32 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) полный список стилей аппаратного контроллера управления.  
  
 *clrFore*  
 Объект **COLORREF** значение, представляющее цвет переднего плана главной панели.  
  
 *clrBack*  
 Объект **COLORREF** значение, представляющее цвет фона главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#1;](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]  
  
##  <a name="create"></a>CReBar::Create  
 Вызовите эту функцию-член для создания главной панели.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на `CWnd` объект которого окно Windows является родительским элементом в строке состояния. Обычно фрейм окна.  
  
 `dwCtrlStyle`  
 Стиль элемента управления главной панели. По умолчанию **RBS_BANDBORDERS**, который отображает ограничить строки для разделения соседних полосами в элементе управления главной панели. В разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список стилей.  
  
 `dwStyle`  
 Стили окна главной панели.  
  
 `nID`  
 Идентификатор главной панели дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CReBar::AddBar](#addbar).  
  
##  <a name="getrebarctrl"></a>CReBar::GetReBarCtrl  
 Эта функция-член предоставляет прямой доступ к базовой стандартного элемента управления.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для использования функциональных возможностей Windows главной панели стандартного элемента управления для настройки вашей главной панели. При вызове `GetReBarCtrl`, он возвращает объект ссылки на `CReBarCtrl` объекта, поэтому можно использовать любой набор функций-членов.  
  
 Дополнительные сведения об использовании `CReBarCtrl` для настройки вашей главной панели, в разделе [CReBarCtrl с помощью](../../mfc/using-crebarctrl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CReBarCtrl&#2;](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCIE](../../visual-cpp-samples.md)   
 [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




