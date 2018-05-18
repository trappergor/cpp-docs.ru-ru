---
title: Класс CPagerCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
dev_langs:
- C++
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d22aa408fe2933803083adc784c2dbf3a85dd4df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cpagerctrl-class"></a>Класс CPagerCtrl
Класс `CPagerCtrl` создается элемент управления страничного навигатора Windows, который может выполнить прокрутку и отобразить содержащееся окно, которое не помещается в содержащее его окно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Создает объект `CPagerCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPagerCtrl::Create](#create)|Создает элемент управления страничного навигатора с указанным стилем и прикрепляет его к текущему `CPagerCtrl` объекта.|  
|[CPagerCtrl::CreateEx](#createex)|Создает элемент управления страничного навигатора с указанным расширенные стили и присоединяет его к текущему `CPagerCtrl` объекта.|  
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Включает или отключает пересылки [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) сообщения окна, которое содержится в текущем элементе управления страничного навигатора.|  
|[CPagerCtrl::GetBkColor](#getbkcolor)|Возвращает цвет фона текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::GetBorder](#getborder)|Получает размер границы текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Получает размер кнопки с текущим элементом управления страничного навигатора.|  
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Получает состояние указанной кнопки в текущий элемент управления страничного навигатора.|  
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Извлекает [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейса для текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Возвращает позицию прокрутки текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Указывает, является ли указанную кнопку текущего элемента управления страничного навигатора в `pressed` состояние.|  
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Указывает, является ли указанную кнопку текущего элемента управления страничного навигатора в `grayed` состояние.|  
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Указывает, является ли указанную кнопку текущего элемента управления страничного навигатора в `hot` состояние.|  
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Указывает, является ли указанную кнопку текущего элемента управления страничного навигатора в `invisible` состояние.|  
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Указывает, является ли указанную кнопку текущего элемента управления страничного навигатора в `normal` состояние.|  
|[CPagerCtrl::RecalcSize](#recalcsize)|Вызывает текущий элемент управления страничного навигатора пересчитать размер автономной окна.|  
|[CPagerCtrl::SetBkColor](#setbkcolor)|Задает цвет фона текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::SetBorder](#setborder)|Задает размер границ текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Задает размер кнопки с текущим элементом управления страничного навигатора.|  
|[CPagerCtrl::SetChild](#setchild)|Задает автономной окна для текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Задает позицию прокрутки текущего элемента управления страничного навигатора.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления страничного навигатора — окно, содержащее другое окно, линейные и больше, чем окна и дает возможность прокрутку и отобразить содержащееся окно. Элемент управления страничного навигатора отображаются две кнопки прокрутки, которые автоматически исчезают при прокрутке содержащееся окно его самый дальний степени и в противном случае на экране. Можно создать элемент управления страничного навигатора, горизонтально или вертикально.  
  
 Например если приложение имеет панель инструментов, недостаточно широкий для отображения всех элементов, панели инструментов можно назначить элемент управления страничного навигатора, и пользователи смогут выполнять прокрутку влево или вправо для доступа ко всем элементов панели инструментов. Microsoft Internet Explorer версии 4.0 (версия commctrl.dll 4.71) представляет элемент управления страничного навигатора.  
  
 `CPagerCtrl` Класс является производным от [CWnd](../../mfc/reference/cwnd-class.md) класса. Дополнительные сведения и пример элемента управления страничного навигатора см. в разделе [элементами управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl  
 Создает объект `CPagerCtrl`.  
  
```  
CPagerCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [CPagerCtrl::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод для создания элемента управления страничного навигатора и присоединить его к `CPagerCtrl` объекта.  
  
##  <a name="create"></a>  CPagerCtrl::Create  
 Создает элемент управления страничного навигатора с указанным стилем и прикрепляет его к текущему `CPagerCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwStyle`|Побитовое сочетание (OR) [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859) для применения к элементу управления.|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления в клиентских координатах.|  
|[in] `pParentWnd`|Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления. Этот параметр не может быть `NULL`.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы создать элемент управления страничного навигатора, объявите `CPagerCtrl` переменной, затем вызовите [CPagerCtrl::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод для этой переменной.  
  
### <a name="example"></a>Пример  
 В следующем примере создается элемент управления страничного навигатора, затем использует [CPagerCtrl::SetChild](#setchild) способ сопоставления очень много кнопке с элементом управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CPagerCtrl::CreateEx  
 Создает элемент управления страничного навигатора с указанным расширенные стили и присоединяет его к текущему `CPagerCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwExStyle`|Побитовое сочетание расширенные стили, которые надо применить к элементу управления. Дополнительные сведения см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) функции.|  
|[in] `dwStyle`|Побитовое сочетание (OR) [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859) для применения к элементу управления.|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления в клиентских координатах.|  
|[in] `pParentWnd`|Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления. Этот параметр не может быть `NULL`.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы создать элемент управления страничного навигатора, объявите `CPagerCtrl` переменной, затем вызовите [CPagerCtrl::Create](#create) или [CPagerCtrl::CreateEx](#createex) метод для этой переменной.  
  
##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse  
 Включает или отключает пересылки [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) сообщения окна, которое содержится в текущем элементе управления страничного навигатора.  
  
```  
void ForwardMouse(BOOL bForward);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `bForward`|`true` для пересылки сообщений мыши или `false` не перенаправлять сообщения мыши.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_FORWARDMOUSE](http://msdn.microsoft.com/library/windows/desktop/bb760867) сообщение, которое описано в Windows SDK.  
  
##  <a name="getborder"></a>  CPagerCtrl::GetBorder  
 Получает размер границы текущего элемента управления страничного навигатора.  
  
```  
int GetBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий размер границы, измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760869) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере используется [CPagerCtrl::GetBorder](#getborder) метод для извлечения толщины границы для элемента управления страничного навигатора.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]  
  
##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor  
 Возвращает цвет фона текущего элемента управления страничного навигатора.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, содержащее текущий цвет фона элемента управления страничного навигатора.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760868) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере используется [CPagerCtrl::SetBkColor](#setbkcolor) метод, чтобы задать цвет фона элемента управления страничного навигатора на красный и [CPagerCtrl::GetBkColor](#getbkcolor) метод Подтверждение изменений.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize  
 Получает размер кнопки с текущим элементом управления страничного навигатора.  
  
```  
int GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий размер кнопки, измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760870) сообщение, которое описано в Windows SDK.  
  
 Если для элемента управления страничного навигатора `PGS_HORZ` стиль, размер кнопки определяет ширину кнопки пролистывания страниц, и если имеется элемент управления страничного навигатора `PGS_VERT` стиль, размер кнопки определяет высоту кнопки страничного навигатора. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState  
 Получает состояние указанную кнопку прокрутки в текущий элемент управления страничного навигатора.  
  
```  
DWORD GetButtonState(int iButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iButton`|Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора `PGS_HORZ`, укажите `PGB_TOPORLEFT` для левую кнопку и `PGB_BOTTOMORRIGHT` для правой кнопки. Если стиль элемента управления страничного навигатора `PGS_VERT`, укажите `PGB_TOPORLEFT` для кнопки top и `PGB_BOTTOMORRIGHT` нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние кнопки, определяемой параметром `iButton` параметр. Состояние — либо `PGF_INVISIBLE`, `PGF_NORMAL`, `PGF_GRAYED`, `PGF_DEPRESSED`, или `PGF_HOT`. Дополнительные сведения см. в разделе разделе возвращают значение [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщение, которое описано в Windows SDK.  
  
##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget  
 Извлекает [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейса для текущего элемента управления страничного навигатора.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IDropTarget` интерфейса для текущего элемента управления страничного навигатора.  
  
### <a name="remarks"></a>Примечания  
 `IDropTarget` — один из интерфейсов, реализуемые для поддержки операций перетаскивания и вставки в приложении.  
  
 Этот метод отправляет [PGM_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb760872) сообщение, которое описано в Windows SDK. Код, вызывающий этот метод отвечает за вызов метода `Release` членом [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) интерфейс, когда интерфейс больше не нужны.  
  
##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos  
 Возвращает позицию прокрутки текущего элемента управления страничного навигатора.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущую позицию прокрутки, измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760874) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере используется [CPagerCtrl::GetScrollPos](#getscrollpos) метод для извлечения текущую позицию прокрутки элемента управления страничного навигатора. Если элемент управления страничного навигатора не прокручивается до нуля, крайней левой позиции в этом примере [CPagerCtrl::SetScrollPos](#setscrollpos) метод, чтобы задать нулевое значение позиции прокрутки.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]  
  
##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed  
 Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в нажатом состоянии.  
  
```  
BOOL IsButtonDepressed(int iButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iButton`|Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора `PGS_HORZ`, укажите `PGB_TOPORLEFT` для левую кнопку и `PGB_BOTTOMORRIGHT` для правой кнопки. Если стиль элемента управления страничного навигатора `PGS_VERT`, укажите `PGB_TOPORLEFT` для кнопки top и `PGB_BOTTOMORRIGHT` нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если указанный кнопка в нажатом состоянии; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщение, которое описано в Windows SDK. Затем он проверяет, является ли состояние, которое возвращается `PGF_DEPRESSED`. Дополнительные сведения см. в разделе разделе возвращают значение [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщения.  
  
##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed  
 Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в состоянии выделена серым цветом.  
  
```  
BOOL IsButtonGrayed(int iButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iButton`|Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора `PGS_HORZ`, укажите `PGB_TOPORLEFT` для левую кнопку и `PGB_BOTTOMORRIGHT` для правой кнопки. Если стиль элемента управления страничного навигатора `PGS_VERT`, укажите `PGB_TOPORLEFT` для кнопки top и `PGB_BOTTOMORRIGHT` нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если указанный кнопка находится в состоянии выделена серым цветом; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщение, которое описано в Windows SDK. Затем он проверяет, является ли состояние, которое возвращается `PGF_GRAYED`. Дополнительные сведения см. в разделе разделе возвращают значение [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщения.  
  
##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot  
 Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в активном состоянии.  
  
```  
BOOL IsButtonHot(int iButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iButton`|Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора `PGS_HORZ`, укажите `PGB_TOPORLEFT` для левую кнопку и `PGB_BOTTOMORRIGHT` для правой кнопки. Если стиль элемента управления страничного навигатора `PGS_VERT`, укажите `PGB_TOPORLEFT` для кнопки top и `PGB_BOTTOMORRIGHT` нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если указанный кнопка находится в активном состоянии; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщение, которое описано в Windows SDK. Затем он проверяет, является ли состояние, которое возвращается `PGF_HOT`. Дополнительные сведения см. в разделе разделе возвращают значение [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщения.  
  
##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible  
 Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в состоянии невидимой.  
  
```  
BOOL IsButtonInvisible(int iButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iButton`|Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора `PGS_HORZ`, укажите `PGB_TOPORLEFT` для левую кнопку и `PGB_BOTTOMORRIGHT` для правой кнопки. Если стиль элемента управления страничного навигатора `PGS_VERT`, укажите `PGB_TOPORLEFT` для кнопки top и `PGB_BOTTOMORRIGHT` нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если указанную кнопку находится в состоянии невидимым; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Windows делает кнопки прокрутки в определенном направлении невидимым при содержащееся окно может прокручиваться его самый дальний степени, так как, нажав кнопку "Дополнительно" не удается подключить несколько содержащееся окно в представление.  
  
 Этот метод отправляет [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщение, которое описано в Windows SDK. Затем он проверяет, является ли состояние, которое возвращается `PGF_INVISIBLE`. Дополнительные сведения см. в разделе разделе возвращают значение [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщения.  
  
### <a name="example"></a>Пример  
 В следующем примере используется [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) метод для определения левого элемента управления страничного навигатора и кнопок прокрутки вправо являются видимыми.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]  
  
##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal  
 Указывает, является ли указанную кнопку прокрутки текущего элемента управления страничного навигатора в обычном состоянии.  
  
```  
BOOL IsButtonNormal(int iButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iButton`|Указывает кнопку, для которого необходимо получить состояние. Если стиль элемента управления страничного навигатора `PGS_HORZ`, укажите `PGB_TOPORLEFT` для левую кнопку и `PGB_BOTTOMORRIGHT` для правой кнопки. Если стиль элемента управления страничного навигатора `PGS_VERT`, укажите `PGB_TOPORLEFT` для кнопки top и `PGB_BOTTOMORRIGHT` нижней кнопки. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если указанной кнопки в обычном состоянии; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщение, которое описано в Windows SDK. Затем он проверяет, является ли состояние, которое возвращается `PGF_NORMAL`. Дополнительные сведения см. в разделе разделе возвращают значение [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) сообщения.  
  
##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize  
 Вызывает текущий элемент управления страничного навигатора пересчитать размер автономной окна.  
  
```  
void RecalcSize();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_RECALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760876) сообщение, которое описано в Windows SDK. Следовательно, отправляет элемент управления страничного навигатора [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) уведомление, чтобы получить размеры прокрутки окна автономной.  
  
### <a name="example"></a>Пример  
 В следующем примере используется [CPagerCtrl::RecalcSize](#recalcsize) метод для запроса к пересчету его размера текущего элемента управления страничного навигатора.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]  
  
### <a name="example"></a>Пример  
 В следующем примере используется [сообщений отражения](../../mfc/tn062-message-reflection-for-windows-controls.md) для включения управления страничного навигатора пересчитать собственный размер, не требуя диалоговое окно родительского элемента управления для выполнения вычисления. Пример является производным `MyPagerCtrl` класса из [CPagerCtrl класса](../../mfc/reference/cpagerctrl-class.md), затем использует схемы сообщений для связывания [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) уведомлений с `OnCalcsize` обработчик уведомлений. В этом примере обработчик уведомлений устанавливает ширину и высоту элемента управления страничного навигатора фиксированного значения.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]  
  
##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor  
 Задает цвет фона текущего элемента управления страничного навигатора.  
  
```  
COLORREF SetBkColor(COLORREF clrBk);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `clrBk`|Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, содержащее новый цвет фона элемента управления страничного навигатора.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, содержащее предыдущий цвет фона элемента управления страничного навигатора.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760878) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере используется [CPagerCtrl::SetBkColor](#setbkcolor) метод, чтобы задать цвет фона элемента управления страничного навигатора на красный и [CPagerCtrl::GetBkColor](#getbkcolor) метод Подтверждение изменений.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="setborder"></a>  CPagerCtrl::SetBorder  
 Задает размер границ текущего элемента управления страничного навигатора.  
  
```  
int SetBorder(int iBorder);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iBorder`|Размер границ новой измеряется в пикселях. Если `iBorder` параметр имеет отрицательное значение, размер границы присваивается нулевое значение.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер границы, измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_SETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760880) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере создается элемент управления страничного навигатора, затем использует [CPagerCtrl::SetChild](#setchild) способ сопоставления очень много кнопке с элементом управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize  
 Задает размер кнопки с текущим элементом управления страничного навигатора.  
  
```  
int SetButtonSize(int iButtonSize);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iButtonSize`|Новый размер кнопки, измеряется в пикселях.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий размер кнопки, измеряется в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_SETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760886) сообщение, которое описано в Windows SDK.  
  
 Если для элемента управления страничного навигатора `PGS_HORZ` стиль, размер кнопки определяет ширину кнопки пролистывания страниц, и если имеется элемент управления страничного навигатора `PGS_VERT` стиль, размер кнопки определяет высоту кнопки страничного навигатора. Размер кнопки по умолчанию — три четверти ширина полосы прокрутки и кнопка минимальный размер составляет 12 пикселей. Дополнительные сведения см. в разделе [стили элемента управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
### <a name="example"></a>Пример  
 В следующем примере создается элемент управления страничного навигатора, затем использует [CPagerCtrl::SetChild](#setchild) способ сопоставления очень много кнопке с элементом управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setchild"></a>  CPagerCtrl::SetChild  
 Задает автономной окна для текущего элемента управления страничного навигатора.  
  
```  
void SetChild(HWND hwndChild);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hwndChild`|Дескриптор окна, которые должны содержаться.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_SETCHILD](http://msdn.microsoft.com/library/windows/desktop/bb760884) сообщение, которое описано в Windows SDK.  
  
 Этот метод не изменяет родительского окна автономной. только элемент управления страничного навигатора для прокрутки назначает дескриптор окна. В большинстве случаев содержащееся окно будет дочернего окна элемента управления страничного навигатора.  
  
### <a name="example"></a>Пример  
 В следующем примере создается элемент управления страничного навигатора, затем использует [CPagerCtrl::SetChild](#setchild) способ сопоставления очень много кнопке с элементом управления страничного навигатора. Затем в примере используется [CPagerCtrl::SetButtonSize](#setbuttonsize) метод, чтобы задать высоту элемента управления страничного навигатора до 20 пикселей и [CPagerCtrl::SetBorder](#setborder) метод, чтобы задать толщину границы в 1 пиксель.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos  
 Задает позицию прокрутки текущего элемента управления страничного навигатора.  
  
```  
void SetScrollPos(int iPos);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iPos`|Новую позицию прокрутки, измеряется в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [PGM_SETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760886) сообщение, которое описано в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CPagerCtrl](../../mfc/reference/cpagerctrl-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Элементы управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760855)



