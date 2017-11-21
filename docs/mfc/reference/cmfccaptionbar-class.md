---
title: "Класс CMFCCaptionBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
dev_langs: C++
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4449ebd1563fe02705913fd4f19e51d195b3d732
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmfccaptionbar-class"></a>Класс CMFCCaptionBar
Объект `CMFCCaptionBar` объект является панель элементов управления, который может отображать три элемента: кнопка, текстовую метку и растровое изображение. Она может содержать только один элемент каждого типа одновременно. Можно выровнять каждый элемент по левому или правому краю элемента управления или по центру. Также можно применить плоский или трехмерный стиль к верхним и нижним границам заголовка окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionBar::Create](#create)|Создает элемент управления панель заголовка и прикрепляет его к `CMFCCaptionBar` объекта.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Указывает, может ли другой области динамической вставки между строке заголовка и родительского фрейма. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|Включает или отключает кнопку на строке заголовка.|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|Возвращает выравнивание указанного элемента.|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Возвращает размер границ заголовка окна.|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Возвращает прямоугольник, ограничивающий кнопки в заголовке окна.|  
|[CMFCCaptionBar::GetMargin](#getmargin)|Возвращает расстояние между границей заголовка панели элементов и границей элемента управления панели заголовка.|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Указывает, является ли заголовок режим панели сообщений.|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Удаляет точечного рисунка из заголовка окна.|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|Удаление кнопки на панели заголовка.|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Удаление значка из заголовка окна.|  
|[CMFCCaptionBar::RemoveText](#removetext)|Удаляет текстовую метку из заголовка окна.|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Задает растровое изображение для заголовка окна.|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Задает размер границ заголовка окна.|  
|[CMFCCaptionBar::SetButton](#setbutton)|Задает кнопки для строки заголовка.|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Указывает, является ли кнопка остается нажатой.|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Задает подсказки для кнопки.|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Задает стиль границы заголовка окна.|  
|[CMFCCaptionBar::SetIcon](#seticon)|Задает значок для строки заголовка.|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Задает всплывающую подсказку для изображения для заголовка окна.|  
|[CMFCCaptionBar::SetMargin](#setmargin)|Задает расстояние между краем элемента панели заголовка и границей элемента управления панели заголовка.|  
|[CMFCCaptionBar::SetText](#settext)|Задает текстовую метку для строки заголовка.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Вызывается платформой для заливки фона строки заголовка.|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Вызывается платформой для отрисовки границ заголовка окна.|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Вызывается платформой для отрисовки кнопки панели заголовка.|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Вызывается платформой для отрисовки изображения панели заголовка.|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Вызывается платформой для отрисовки текста строки заголовка.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Цвет фона строки заголовка.|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Цвет границы заголовка окна.|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Цвет текста строки заголовка.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать заголовок окна, выполните следующие действия.  
  
1.  Создать `CMFCCaptionBar` объекта. Как правило необходимо добавить заголовок в класс окна фрейма.  
  
2.  Вызовите [CMFCCaptionBar::Create](#create) метод для создания элемента управления панель заголовка и присоединить его к `CMFCCaptionBar` объекта.  
  
3.  Вызовите [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), и [CMFCCaptionBar::SetBitmap](#setbitmap)присваивать элементам панели заголовка.  
  
 При установке элемент button, необходимо назначить идентификатор команды кнопки. Когда пользователь нажимает эту кнопку, маршруты панель заголовка `WM_COMMAND` сообщения, которые содержат этот идентификатор в родительское окно фрейма.  
  
 Заголовок также можно работать в режиме панели сообщений, который эмулирует панели сообщений, которое отображается в приложениях Microsoft Office 2007. В режиме панели сообщений строке заголовка отображает растровое изображение, сообщения и кнопки (который обычно открывает диалоговое окно.) Можно назначить всплывающей подсказки к растровому изображению.  
  
 Чтобы включить режим панели сообщений, вызовите [CMFCCaptionBar::Create](#create) и четвертый параметр (bIsMessageBarMode) равен `TRUE`.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCCaptionBar` класса. В примере показано создание элемента управления панель заголовка, задать визуально трехмерную границу заголовка окна, задайте расстояние в пикселях между границей заголовка панели элементов и границей элемента управления панель заголовка, кнопки для строки заголовка , задать подсказки для кнопки, задайте текстовую метку для строки заголовка, растровое изображение для заголовка окна и всплывающей подсказкой для изображения в строке заголовка. Этот фрагмент кода является частью [MS Office 2007 демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcaptionbar.h  
  
##  <a name="create"></a>CMFCCaptionBar::Create  
 Создает элемент управления панель заголовка и прикрепляет его к `CMFCCaptionBar` объекта.  
  
```  
BOOL Create(
    DWORD dwStyle,  
    CWnd* pParentWnd,  
    UINT uID,  
    int nHeight=-1,  
    BOOL bIsMessageBarMode=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Сочетание логического или стили полосы заголовка.  
  
 `pParentWnd`  
 Родительское окно элемента управления панели заголовка.  
  
 `uID`  
 Идентификатор элемента управления панели заголовка.  
  
 `nHeight`  
 Высота в пикселях панель заголовка элемента управления. Если это значение -1, высота вычисляется в соответствии с Высота значка, текст и кнопки, которая отображает элемент управления панели заголовка.  
  
 `bIsMessageBarMode`  
 `TRUE`Если заголовок находится в режиме панель сообщений. `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент управления панель заголовка создан успешно; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Создании `CMFCCaptionBar` объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `Create` метод, который создает элемент управления Windows и прикрепляет его к `CMFCCaptionBar` объекта.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore  
 Указывает, может ли другой области динамической вставки между строке заголовка и родительского фрейма.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `FALSE` Если не переопределено.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablebutton"></a>CMFCCaptionBar::EnableButton  
 Включает или отключает кнопку на строке заголовка.  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить кнопку, `FALSE` для выключения кнопки.  
  
##  <a name="getalignment"></a>CMFCCaptionBar::GetAlignment  
 Возвращает выравнивание указанного элемента.  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `elem`  
 Элемент строки подписи, для которого требуется извлечь выравнивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выравнивание элемента, например кнопки, растровое изображение, текст или значок.  
  
### <a name="remarks"></a>Примечания  
 Выравнивание элемента может принимать одно из следующих значений:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize  
 Возвращает размер границ заголовка окна.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в пикселях границы.  
  
##  <a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect  
 Возвращает прямоугольник, ограничивающий кнопки в заголовке окна.  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , содержащий координаты ограничивающего прямоугольника кнопки в заголовке окна.  
  
##  <a name="getmargin"></a>CMFCCaptionBar::GetMargin  
 Возвращает расстояние между границей заголовка панели элементов и границей элемента управления панели заголовка.  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расстояние в пикселях между границей заголовка панели элементов и границей элемента управления панели заголовка.  
  
##  <a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode  
 Указывает, является ли заголовок режим панели сообщений.  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если заголовок находится в режиме панель сообщений. `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 В режиме строки сообщения заголовок отображает изображение всплывающей подсказки, текст сообщения и кнопки.  
  
##  <a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground  
 Цвет фона строки заголовка.  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder  
 Цвет границы заголовка окна.  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText  
 Цвет текста строки заголовка.  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground  
 Вызывается платформой для заливки фона строки заголовка.  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства заголовка окна.  
  
 [in] `rect`  
 Ограничивающий прямоугольник для заливки.  
  
### <a name="remarks"></a>Примечания  
 `OnDrawBackground` Метод вызывается, когда заполняется фона строки заголовка. Реализация по умолчанию заливке фона с помощью [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) цвет.  
  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид заголовка окна.  
  
##  <a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder  
 Вызывается платформой для отрисовки границ заголовка окна.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, который используется для отображения границ.  
  
 [in] `rect`  
 Ограничивающий прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию, имеют плоский стиль границы.  
  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид границ заголовка окна.  
  
##  <a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton  
 Вызывается платформой для отрисовки кнопки панели заголовка.  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, который используется для отображения кнопки.  
  
 [in] `rect`  
 Ограничивающий прямоугольник кнопки.  
  
 [in] `strButton`  
 Текстовая подпись кнопки.  
  
 [in] `bEnabled`  
 `TRUE`Если кнопка включена; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид кнопки заголовка окна.  
  
##  <a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage  
 Вызывается платформой для отрисовки изображения панели заголовка.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, который используется для отображения изображения.  
  
 [in] `rect`  
 Указывает ограничивающий прямоугольник для изображения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид изображения.  
  
##  <a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText  
 Вызывается платформой для отрисовки текста строки заголовка.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, который используется для отображения кнопки.  
  
 [in] `rect`  
 Ограничивающий прямоугольник для текста.  
  
 [in] `strText`  
 Текстовая строка для отображения.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отображается текст с помощью `CDC::DrawText` и [CMFCCaptionBar::m_clrBarText](#m_clrbartext) цвет.  
  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид текста в строке заголовка.  
  
##  <a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap  
 Удаляет точечного рисунка из заголовка окна.  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>CMFCCaptionBar::RemoveButton  
 Удаление кнопки на панели заголовка.  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>Примечания  
 Макет панели элементов заголовка настраиваются автоматически.  
  
##  <a name="removeicon"></a>CMFCCaptionBar::RemoveIcon  
 Удаление значка из заголовка окна.  
  
```  
void RemoveIcon();
```  
  
##  <a name="removetext"></a>CMFCCaptionBar::RemoveText  
 Удаляет текстовую метку из заголовка окна.  
  
```  
void RemoveText();
```  
  
##  <a name="setbitmap"></a>CMFCCaptionBar::SetBitmap  
 Задает растровое изображение для заголовка окна.  
  
```  
void SetBitmap(
    HBITMAP hBitmap,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

 
void SetBitmap(
    UINT uiBmpResID,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hBitmap`  
 Дескриптор точечного рисунка для установки.  
  
 [in] `clrTransparent`  
 Значение RGB определяет прозрачный цвет изображения.  
  
 [in] `bStretch`  
 Если `TRUE`, точечный рисунок растягивается, если не помещается в образ, ограничивающего прямоугольника. В противном случае не растягивается растрового изображения.  
  
 [in] `bmpAlignment`  
 Выравнивание растрового изображения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для задания растровое изображение на заголовок окна.  
  
 Автоматически уничтожается предыдущих растрового изображения. Если заголовок отображается значок, поскольку вы присвоили [CMFCCaptionBar::SetIcon](#seticon) метод, точечный рисунок не будет отображаться, пока не будет удален значок путем вызова [CMFCCaptionBar::RemoveIcon](#removeicon).  
  
 Выравнивается точечного рисунка, который задается параметром `bmpAlignment` параметр.  Этот параметр может принимать одно из следующих значений `BarElementAlignment`:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize  
 Задает размер границ заголовка окна.  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nSize`  
 Новый размер в пикселях границы панели заголовка.  
  
##  <a name="setbutton"></a>CMFCCaptionBar::SetButton  
 Задает кнопки для строки заголовка.  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszLabel`  
 Метка кнопки команды.  
  
 `uiCmdUI`  
 Идентификатор команды кнопки.  
  
 `btnAlignmnet`  
 Выравнивание кнопок.  
  
 `bHasDropDownArrow`  
 `TRUE`Если кнопка отображает стрелку раскрывающегося списка, `FALSE` в противном случае.  
  
##  <a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed  
 Указывает, является ли кнопка остается нажатой.  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bPresed`  
 `TRUE`Если кнопки отслеживает его нажаты `FALSE` в противном случае.  
  
##  <a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip  
 Задает подсказки для кнопки.  
  
```  
void SetButtonToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszToolTip`  
 Заголовок подсказки.  
  
 [in] `lpszDescription`  
 Описание элемента tooltip.  
  
##  <a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder  
 Задает стиль границы заголовка окна.  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bFlat`  
 `TRUE`Если границы заголовка окна, остается неизменным. `FALSE`Если границы 3D.  
  
##  <a name="seticon"></a>CMFCCaptionBar::SetIcon  
 Задает значок для строки заголовка.  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hIcon`  
 Дескриптор значка для задания.  
  
 [in] `iconAlignment`  
 Выравнивание значка.  
  
### <a name="remarks"></a>Примечания  
 Заголовки можно отобразить значков и точечных рисунков. В разделе [CMFCCaptionBar::SetBitmap](#setbitmap) чтобы узнать, как отобразить растровое изображение. Если задать значок и растровое изображение, значок отображается всегда. Вызовите [CMFCCaptionBar::RemoveIcon](#removeicon) Удаление значка из заголовка окна.  
  
 Значок, выровненный по `iconAlignment` параметр. Он может принимать одно из следующих `BarElementAlignment` значения:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip  
 Задает всплывающую подсказку для изображения в строке заголовка.  
  
```  
void SetImageToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszToolTip`  
 Текст всплывающей подсказки.  
  
 [in] `lpszDescription`  
 Описание элемента tooltip.  
  
##  <a name="setmargin"></a>CMFCCaptionBar::SetMargin  
 Задает расстояние между краем элемента панели заголовка и границей элемента управления панели заголовка.  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMargin`  
 Расстояние в пикселях между границей заголовка панели элементов и границей элемента управления панели заголовка.  
  
##  <a name="settext"></a>CMFCCaptionBar::SetText  
 Задает текстовую метку для строки заголовка.  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strText`  
 Текстовая строка для установки.  
  
 [in] `textAlignment`  
 Выравнивание текста.  
  
### <a name="remarks"></a>Примечания  
 Выравнивание текстовой подписи, который задается параметром `textAlignment` параметр. Он может принимать одно из следующих `BarElementAlignment` значения:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
