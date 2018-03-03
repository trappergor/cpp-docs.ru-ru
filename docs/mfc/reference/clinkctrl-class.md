---
title: "Класс классах-оболочках | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6834190d7693e60f80285b04a04c484313d3c2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="clinkctrl-class"></a>Класс классах-оболочках
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
|[CLinkCtrl::Create](#create)|Создает элемент управления для связи и прикрепляет его к `CLinkCtrl` объекта.|  
|[CLinkCtrl::CreateEx](#createex)|Создает элемент управления для связи с расширенные стили и прикрепляет его к `CLinkCtrl` объекта.|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Извлекает идеальную высоту элемента управления ссылки.|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|Вычисляет предпочтительную высоту текст ссылки для текущего элемента управления ссылки, в зависимости от заданной ширины по ссылке.|  
|[CLinkCtrl::GetItem](#getitem)|Извлекает состояние и атрибуты элемента управления ссылки.|  
|[CLinkCtrl::GetItemID](#getitemid)|Возвращает идентификатор элемента управления ссылки.|  
|[CLinkCtrl::GetItemState](#getitemstate)|Получает состояние элемента управления ссылки.|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|Получает URL-адрес, представленный ссылку элемента управления.|  
|[CLinkCtrl::HitTest](#hittest)|Определяет, является ли пользователь щелкнул указанная ссылка.|  
|[CLinkCtrl::SetItem](#setitem)|Задает состояний и атрибуты элемента управления ссылки.|  
|[CLinkCtrl::SetItemID](#setitemid)|Задает идентификатор элемента управления ссылки.|  
|[CLinkCtrl::SetItemState](#setitemstate)|Задает состояние элемента управления ссылки.|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|Задает URL-адрес представлена ссылка элементом управления.|  
  
## <a name="remarks"></a>Примечания  
 «Связать элемент управления» предоставляет удобный способ внедрения гипертекстовые ссылки в окне. Фактический элемент управления — это окно, который отображает текст более и запускает соответствующие приложения, когда пользователь щелкает ссылку. Несколько связей, поддерживаются в пределах одного элемента управления и может осуществляться отсчитываемый от нуля индекс.  
  
 Этот элемент управления (и, следовательно, `CLinkCtrl` класс) доступен только для программ, работающих под управлением Windows XP и более поздних версий.  
  
 Дополнительные сведения см. в разделе [управления SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="clinkctrl"></a>CLinkCtrl::CLinkCtrl  
 Создает объект `CLinkCtrl`.  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>CLinkCtrl::Create  
 Создает элемент управления для связи и прикрепляет его к `CLinkCtrl` объекта.  
  
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
 `lpszLinkMarkup`  
 Указатель нулем строка, содержащая помеченные текст для отображения. Дополнительные сведения см. в подразделе «Доступ разметки и ссылки» раздела [Обзор управления SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 `dwStyle`  
 Задает стиль элемента управления ссылки. Примените любое сочетание стилей элемента управления. В разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в `Windows SDK` для получения дополнительной информации.  
  
 `rect`  
 Задает размер и положение элемента управления ссылки. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления ссылки. Он не должен быть `NULL`.  
  
 `nID`  
 Указывает идентификатор элемента управления ссылки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если инициализация выполнена успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Создании `CLinkCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает ссылку элемента управления и прикрепляет его к `CLinkCtrl` объекта. Если вы хотите использовать с элементом управления windows расширенных стилей, вызовите [CLinkCtrl::CreateEx](#createex) вместо `Create`.  
  
 Во второй форме `Create` метод является устаревшим. Использовать первую форму, указывающее `lpszLinkMarkup` параметра.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяет две переменные с именем `m_Link1` и `m_Link2`, которые используются для доступа к двух элементов управления связями.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода создается одного элемента управления ссылки, исходя из расположения другого элемента управления ссылки. При запуске приложения, загрузчик ресурсов создает первого элемента управления ссылки. Когда приложение входит OnInitDialog-метод, создания второго элемента управления ссылки относительно позиции первого элемента управления ссылки. Затем измените размер второго элемента управления ссылки в соответствии с текстом, который он отображает.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CLinkCtrl::CreateEx  
 Создает элемент управления для связи с расширенные стили и прикрепляет его к `CLinkCtrl` объекта.  
  
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
 `lpszLinkMarkup`  
 Указатель нулем строка, содержащая помеченные текст для отображения. Дополнительные сведения см. в подразделе «Доступ разметки и ссылки» раздела [Обзор управления SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 `dwExStyle`  
 Указывает расширенный стиль элемента управления ссылки. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 `dwStyle`  
 Задает стиль элемента управления ссылки. Примените любое сочетание стилей элемента управления. Дополнительные сведения см. в разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в Windows SDK.  
  
 `rect`  
 Задает размер и положение элемента управления ссылки. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления ссылки. Он не должен быть `NULL`.  
  
 `nID`  
 Указывает идентификатор элемента управления ссылки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если инициализация выполнена успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) применения расширенных констант стиль Windows.  
  
 Во второй форме `CreateEx` метод является устаревшим. Использовать первую форму, указывающее `lpszLinkMarkup` параметра.  
  
##  <a name="getidealheight"></a>CLinkCtrl::GetIdealHeight  
 Извлекает идеальную высоту элемента управления ссылки.  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идеальная высота элемента управления в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716), как описано в Windows SDK.  
  
##  <a name="getidealsize"></a>CLinkCtrl::GetIdealSize  
 Вычисляет предпочтительную высоту текст ссылки для текущего элемента управления ссылки, в зависимости от заданной ширины по ссылке.  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `cxMaxWidth`|Максимальная ширина ссылки, в пикселях.|  
|[out] *`pSize`|Указатель на Windows [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры. По возвращении из этого метода `cy` членом `SIZE` структура содержит Высота текстового идеальный ссылку для ширину текста ссылки, задаваемый `cxMaxWidth`. `cx` Член структуры содержит ширину текста ссылки, которая фактически требуется.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предпочтительная высота текста ссылки, в пикселях. Возвращаемое значение является таким же, как значение `cy` членом `SIZE` структуры.  
  
### <a name="remarks"></a>Примечания  
 Пример `GetIdealSize` метода, см. пример в [CLinkCtrl::Create](#create).  
  
 Этот метод отправляет [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718) сообщение, которое описано в Windows SDK.  
  
##  <a name="getitem"></a>CLinkCtrl::GetItem  
 Извлекает состояние и атрибуты элемента управления ссылки.  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) структуру для получения сведений об элементе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720), как описано в Windows SDK.  
  
##  <a name="getitemid"></a>CLinkCtrl::GetItemID  
 Возвращает идентификатор элемента управления ссылки.  
  
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
 `iLink`  
 Индекс элемента управления ссылки.  
  
 *strID*  
 Объект [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий идентификатор указанного элемента.  
  
 *szID*  
 Нулем строка, содержащая идентификатор указанного элемента.  
  
 *cchID*  
 Размер в символах *szID* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
> [!NOTE]
>  Эта функция также возвращает **FALSE** если буфер *szID или strID* меньше, чем **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Примечания  
 Возвращает идентификатор элемента управления определенному каналу. Дополнительные сведения см. в разделе сообщение Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) в Windows SDK.  
  
##  <a name="getitemstate"></a>CLinkCtrl::GetItemState  
 Получает состояние элемента управления ссылки.  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `iLink`  
 Индекс элемента управления ссылки.  
  
 `pnState`  
 Значение элемента указанного состояния.  
  
 `stateMask`  
 Сочетание флаги, описывающие элементы состояния для получения. Список значений, см. в описании **состояние** члена в [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) структуры. Допустимые элементы идентичны допускается в **состояние**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Получает значение элемента состояния указанного элемента управления определенному каналу. Дополнительные сведения см. в разделе сообщение Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) в Windows SDK.  
  
##  <a name="getitemurl"></a>CLinkCtrl::GetItemUrl  
 Получает URL-адрес, представленный ссылку элемента управления.  
  
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
 `iLink`  
 Индекс элемента управления ссылки.  
  
 `strUrl`  
 Объект [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес, представленный указанным элементом  
  
 `szUrl`  
 Символом null строку, содержащую URL-адрес, представленный указанным элементом  
  
 *cchUrl*  
 Размер в символах *szURL* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
> [!NOTE]
>  Эта функция также возвращает **FALSE** если буфер *szUrl или strUrl* меньше, чем **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Примечания  
 Получает URL-адрес, представленный указанную ссылку на элемент управления. Дополнительные сведения см. в разделе сообщение Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) в Windows SDK.  
  
##  <a name="hittest"></a>CLinkCtrl::HitTest  
 Определяет, если пользователь щелкнул указанная ссылка.  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *phti*  
 Указатель на **LHITTESTINFO** структуру, содержащую все сведения о ссылке пользователь щелкнул.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722), как описано в Windows SDK.  
  
##  <a name="setitem"></a>CLinkCtrl::SetItem  
 Задает состояний и атрибуты элемента управления ссылки.  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) структуру, содержащую сведения для установки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724), как описано в Windows SDK.  
  
##  <a name="setitemid"></a>CLinkCtrl::SetItemID  
 Возвращает идентификатор элемента управления ссылки.  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>Параметры  
 `iLink`  
 Индекс элемента управления ссылки.  
  
 *szID*  
 Нулем строка, содержащая идентификатор указанного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Задает идентификатор элемента управления определенному каналу. Дополнительные сведения см. в разделе сообщение Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) в Windows SDK.  
  
##  <a name="setitemstate"></a>CLinkCtrl::SetItemState  
 Получает состояние элемента управления ссылки.  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>Параметры  
 `iLink`  
 Индекс элемента управления ссылки.  
  
 `pnState`  
 Значение устанавливается элемента указанного состояния.  
  
 `stateMask`  
 Сочетание флагов, описывающий значение элемента состояния. Список значений, см. в описании **состояние** члена в [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) структуры. Допустимые элементы идентичны допускается в **состояние**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Задает значение элемента состояния указанного элемента управления определенному каналу. Дополнительные сведения см. в разделе сообщение Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) в Windows SDK.  
  
##  <a name="setitemurl"></a>CLinkCtrl::SetItemUrl  
 Задает URL-адрес представлена ссылка элементом управления.  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>Параметры  
 `iLink`  
 Индекс элемента управления ссылки.  
  
 `szUrl`  
 Символом null строку, содержащую URL-адрес, представленный указанным элементом  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Задает URL-адрес, представленный указанную ссылку на элемент управления. Дополнительные сведения см. в разделе сообщение Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
