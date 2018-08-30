---
title: Класс CLinkCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 422326f03674c541c4fdc45529bee45bf0ff5df6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201008"
---
# <a name="clinkctrl-class"></a>Класс CLinkCtrl
Предоставляет функциональные возможности стандартного элемента управления SysLink Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|Создает объект `CLinkCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|Создает элемент управления связями и присоединяет его к `CLinkCtrl` объекта.|  
|[CLinkCtrl::CreateEx](#createex)|Создает элемент управления связями с помощью расширенных стилей и присоединяет его к `CLinkCtrl` объекта.|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Извлекает Идеальная высота элемента управления ссылки.|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|Вычисляет предпочтительную высоту текст ссылки для текущего управления ссылками, в зависимости от заданной ширины ссылку.|  
|[CLinkCtrl::GetItem](#getitem)|Извлекает состояния и атрибуты элемента управления ссылки.|  
|[CLinkCtrl::GetItemID](#getitemid)|Извлекает идентификатор элемента управления ссылки.|  
|[CLinkCtrl::GetItemState](#getitemstate)|Извлекает состояние элемента управления ссылки.|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|Извлекает URL-адрес, представленный элемент управления ссылки.|  
|[CLinkCtrl::HitTest](#hittest)|Определяет, является ли пользователь щелкнул указанную ссылку.|  
|[CLinkCtrl::SetItem](#setitem)|Задает состояний и атрибуты элемента управления ссылки.|  
|[CLinkCtrl::SetItemID](#setitemid)|Задает идентификатор элемента управления ссылки.|  
|[CLinkCtrl::SetItemState](#setitemstate)|Задает состояние элемента управления ссылки.|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|Задает URL-адрес, представленный элемент управления ссылки.|  
  
## <a name="remarks"></a>Примечания  
 «Связать элемент управления» предоставляет удобный способ внедрения в окно гипертекстовых ссылок. Фактический элемент управления является окном, который визуализирует текст более и запускает соответствующие приложения, когда пользователь щелкает ссылку. Несколько ссылок, поддерживаются в пределах одного элемента управления и может осуществляться отсчитываемый от нуля индекс.  
  
 Этот элемент управления (и, следовательно `CLinkCtrl` класс) доступен только для программ, работающих под управлением Windows XP и более поздних версий.  
  
 Дополнительные сведения см. в разделе [управления SysLink](/windows/desktop/Controls/syslink-overview) в пакете Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="clinkctrl"></a>  CLinkCtrl::CLinkCtrl  
 Создает объект `CLinkCtrl`.  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>  CLinkCtrl::Create  
 Создает элемент управления связями и присоединяет его к `CLinkCtrl` объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszLinkMarkup*  
 Указатель на строку с завершающим нулевым символом, содержащий помеченной текст для отображения. Дополнительные сведения см. в разделе «Доступ разметки и ссылку» в разделе [Обзор управления SysLink](/windows/desktop/Controls/syslink-overview).  
  
 *dwStyle*  
 Задает стиль ссылки элемента управления. Примените любое сочетание стилей элемента управления. См. в разделе [общие стили элемента управления](/windows/desktop/Controls/common-control-styles) в `Windows SDK` Дополнительные сведения.  
  
 *Rect*  
 Задает размер и положение элемента управления ссылки. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 *pParentWnd*  
 Указывает родительскому окну элемента связи. Он не должен иметь значение NULL.  
  
 *nID*  
 Указывает идентификатор элемента управления ссылки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если инициализация прошла успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 При создании `CLinkCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает управления ссылками и присоединяет его к `CLinkCtrl` объекта. Если вы хотите использовать windows расширенных стилей с элементом управления, вызовите [CLinkCtrl::CreateEx](#createex) вместо `Create`.  
  
 Вторая форма `Create` метод считается устаревшим. Использовать первую форму, указывающее *lpszLinkMarkup* параметра.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяет две переменные, с именем `m_Link1` и `m_Link2`, которые используются для доступа к двух элементов управления связей.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода создается один элемент управления ссылки на основе расположения другого элемента управления ссылки. Загрузчик ресурсов создает первый элемент управления ссылку при запуске приложения. Когда приложение входит OnInitDialog-метод, создании второй элемент управления ссылки относительно позиции первого элемента управления ссылки. Затем измените размеры второй элемент управления ссылки в соответствии с текстом, который он отображает.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CLinkCtrl::CreateEx  
 Создает элемент управления связями с помощью расширенных стилей и присоединяет его к `CLinkCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszLinkMarkup*  
 Указатель на строку с завершающим нулевым символом, содержащий помеченной текст для отображения. Дополнительные сведения см. в разделе «Доступ разметки и ссылку» в разделе [Обзор управления SysLink](/windows/desktop/Controls/syslink-overview).  
  
 *dwExStyle*  
 Указывает расширенный стиль элемента управления ссылки. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) в пакете Windows SDK.  
  
 *dwStyle*  
 Задает стиль ссылки элемента управления. Примените любое сочетание стилей элемента управления. Дополнительные сведения см. в разделе [общие стили элемента управления](/windows/desktop/Controls/common-control-styles) в пакете Windows SDK.  
  
 *Rect*  
 Задает размер и положение элемента управления ссылки. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 *pParentWnd*  
 Указывает родительскому окну элемента связи. Он не должен иметь значение NULL.  
  
 *nID*  
 Указывает идентификатор элемента управления ссылки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если инициализация прошла успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) применения расширенной констант стиля Windows.  
  
 Вторая форма `CreateEx` метод считается устаревшим. Использовать первую форму, указывающее *lpszLinkMarkup* параметра.  
  
##  <a name="getidealheight"></a>  CLinkCtrl::GetIdealHeight  
 Извлекает Идеальная высота элемента управления ссылки.  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идеальная высота элемента управления в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [LM_GETIDEALHEIGHT](/windows/desktop/Controls/lm-getidealheight), как описано в пакете Windows SDK.  
  
##  <a name="getidealsize"></a>  CLinkCtrl::GetIdealSize  
 Вычисляет предпочтительную высоту текст ссылки для текущего управления ссылками, в зависимости от заданной ширины ссылку.  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *cxMaxWidth*|Максимальная ширина ссылки, в пикселях.|  
|[out] \* *pSize*|Указатель на Windows [размер](https://msdn.microsoft.com/library/windows/desktop/dd145106) структуры. При возвращении данного метода *cy* членом `SIZE` структура содержит Высота текстового идеальный ссылку для ширину текста ссылки, который задается параметром *cxMaxWidth*. *Cx* член структуры содержит ширину текста ссылки, которая фактически требуется.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предпочтительная высота текста ссылки, в пикселях. Возвращаемое значение является таким же, как значение *cy* членом `SIZE` структуры.  
  
### <a name="remarks"></a>Примечания  
 Пример `GetIdealSize` метод, см. пример в [CLinkCtrl::Create](#create).  
  
 Этот метод отправляет [LM_GETIDEALSIZE](/windows/desktop/Controls/lm-getidealsize) сообщения, который описан в пакете Windows SDK.  
  
##  <a name="getitem"></a>  CLinkCtrl::GetItem  
 Извлекает состояния и атрибуты элемента управления ссылки.  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pItem*  
 Указатель на [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) структуру для получения сведений об элементе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [LM_GETITEM](/windows/desktop/Controls/lm-getitem), как описано в пакете Windows SDK.  
  
##  <a name="getitemid"></a>  CLinkCtrl::GetItemID  
 Извлекает идентификатор элемента управления ссылки.  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *iLink*  
 Индекс ссылки элемента управления.  
  
 *strID*  
 Объект [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий идентификатор указанного элемента.  
  
 *szID*  
 Завершающаяся нулем строка, содержащая идентификатор указанного элемента.  
  
 *cchID*  
 Размер в символах *szID* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
> [!NOTE]
>  Эта функция также возвращает значение FALSE, если буфер *szID или strID* меньше, чем MAX_LINKID_TEXT.  
  
### <a name="remarks"></a>Примечания  
 Извлекает идентификатор элемента управления определенной ссылки. Дополнительные сведения см. в разделе сообщение Win32 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) в пакете Windows SDK.  
  
##  <a name="getitemstate"></a>  CLinkCtrl::GetItemState  
 Извлекает состояние элемента управления ссылки.  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *iLink*  
 Индекс ссылки элемента управления.  
  
 *pnState*  
 Значение элемента указанного состояния.  
  
 *stateMask*  
 Сочетание флаги, описывающие элемент состояния для получения. Список значений, см. в описании `state` члена в [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) структуры. Допустимые элементы аналогичны используемым в `state`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Получает значение элемента указанного состояния элемента управления определенной ссылки. Дополнительные сведения см. в разделе сообщение Win32 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) в пакете Windows SDK.  
  
##  <a name="getitemurl"></a>  CLinkCtrl::GetItemUrl  
 Извлекает URL-адрес, представленный элемент управления ссылки.  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *iLink*  
 Индекс ссылки элемента управления.  
  
 *strUrl*  
 Объект [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес, представленный указанным элементом  
  
 *szUrl*  
 Заканчивающуюся нулем строку, содержащую URL-адрес, представленный указанным элементом  
  
 *cchUrl*  
 Размер в символах *szURL* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
> [!NOTE]
>  Эта функция также возвращает значение FALSE, если буфер *szUrl или strUrl* меньше, чем MAX_LINKID_TEXT.  
  
### <a name="remarks"></a>Примечания  
 Извлекает URL-адрес, представленный указанную ссылку на элемент управления. Дополнительные сведения см. в разделе сообщение Win32 [LM_GETITEM](/windows/desktop/Controls/lm-getitem) в пакете Windows SDK.  
  
##  <a name="hittest"></a>  CLinkCtrl::HitTest  
 Определяет, если пользователь щелкнул указанной ссылки.  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *phti*  
 Указатель на `LHITTESTINFO` структуру, содержащую все сведения о ссылке пользователь щелкнул.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [LM_HITTEST](/windows/desktop/Controls/lm-hittest), как описано в пакете Windows SDK.  
  
##  <a name="setitem"></a>  CLinkCtrl::SetItem  
 Задает состояний и атрибуты элемента управления ссылки.  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pItem*  
 Указатель на [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) структуру, содержащую сведения для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [LM_SETITEM](/windows/desktop/Controls/lm-setitem), как описано в пакете Windows SDK.  
  
##  <a name="setitemid"></a>  CLinkCtrl::SetItemID  
 Извлекает идентификатор элемента управления ссылки.  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>Параметры  
 *iLink*  
 Индекс ссылки элемента управления.  
  
 *szID*  
 Завершающаяся нулем строка, содержащая идентификатор указанного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Задает идентификатор элемента управления определенной ссылки. Дополнительные сведения см. в разделе сообщение Win32 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) в пакете Windows SDK.  
  
##  <a name="setitemstate"></a>  CLinkCtrl::SetItemState  
 Извлекает состояние элемента управления ссылки.  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>Параметры  
 *iLink*  
 Индекс ссылки элемента управления.  
  
 *pnState*  
 Значение, задаваемое элемента указанное состояние.  
  
 *stateMask*  
 Сочетание флагов, описывающий элемент состояния задания. Список значений, см. в описании `state` члена в [LITEM](/windows/desktop/api/commctrl/ns-commctrl-taglitem) структуры. Допустимые элементы аналогичны используемым в `state`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Задает значение элемента состояния указанного элемента управления определенной ссылки. Дополнительные сведения см. в разделе сообщение Win32 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) в пакете Windows SDK.  
  
##  <a name="setitemurl"></a>  CLinkCtrl::SetItemUrl  
 Задает URL-адрес, представленный элемент управления ссылки.  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>Параметры  
 *iLink*  
 Индекс ссылки элемента управления.  
  
 *szUrl*  
 Заканчивающуюся нулем строку, содержащую URL-адрес, представленный указанным элементом  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Задает URL-адрес, представленный указанную ссылку на элемент управления. Дополнительные сведения см. в разделе сообщение Win32 [LM_SETITEM](/windows/desktop/Controls/lm-setitem) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
