---
title: "Класс CMFCCaptionBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionBar class
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c9be93449392de9d04e4869db8dcd73e08125c88
ms.lasthandoff: 02/24/2017

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
|[CMFCCaptionBar::Create](#create)|Создает элемент управления панель заголовка и присоединяет его к `CMFCCaptionBar` объекта.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Указывает, может ли другой области динамически вставляются между строки заголовка и его родительского фрейма. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|Включает или отключает кнопку в заголовке окна.|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|Возвращает выравнивание указанного элемента.|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Возвращает размер границы заголовка окна.|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Возвращает прямоугольник, ограничивающий кнопки в строке заголовка.|  
|[CMFCCaptionBar::GetMargin](#getmargin)|Возвращает расстояние между границей заголовка панели элементов и границей элемента управления заголовка строки.|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Указывает, является ли заголовок в режиме панель сообщений.|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Удаляет растрового изображения из заголовка окна.|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|Удаление кнопки в строке заголовка.|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Удаление значка из заголовка окна.|  
|[CMFCCaptionBar::RemoveText](#removetext)|Удаляет текстовую метку из заголовка окна.|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Задает растровое изображение для заголовка окна.|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Задает размер границы заголовка окна.|  
|[CMFCCaptionBar::SetButton](#setbutton)|Задает кнопку для строки заголовка.|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Указывает, является ли кнопка остается нажатой.|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Задает подсказки для кнопки.|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Задает стиль границы заголовка окна.|  
|[CMFCCaptionBar::SetIcon](#seticon)|Задает значок для строки заголовка.|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Задает всплывающую подсказку для изображения заголовка окна.|  
|[CMFCCaptionBar::SetMargin](#setmargin)|Задает расстояние между краем элемента панель заголовка и краем элемента управления заголовка строки.|  
|[CMFCCaptionBar::SetText](#settext)|Задает текстовую метку для строки заголовка.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Вызывается платформой для заполнения фона заголовка окна.|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Вызывается платформой для рисования границы заголовка окна.|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Вызывается платформой для отрисовки кнопки в строке заголовка.|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Вызывается платформой для рисования изображения панели заголовка.|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Вызывается платформой для рисования текста строки заголовка.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Цвет фона заголовка окна.|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Цвет границы заголовка окна.|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Цвет текста заголовка строки.|  
  
## <a name="remarks"></a>Примечания  
 Создание заголовка окна, выполните следующие действия.  
  
1.  Создать `CMFCCaptionBar` объекта. Как правило необходимо добавить заголовок в класс окна фрейма.  
  
2.  Вызов [CMFCCaptionBar::Create](#create) метод для создания заголовка панели управления и присоединить его к `CMFCCaptionBar` объекта.  
  
3.  Вызов [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), и [CMFCCaptionBar::SetBitmap](#setbitmap) для задания заголовка панели элементов.  
  
 Если значение элемента button, необходимо назначить идентификатор команды кнопки. Когда пользователь нажимает эту кнопку, маршруты панель заголовка `WM_COMMAND` сообщения, этот идентификатор родительского фрейма окна.  
  
 Заголовок также можно работать в режиме панель сообщений, который эмулирует панели сообщения, которая отображается в приложениях Microsoft Office 2007. В режим панели сообщения заголовок отображается точечный рисунок, сообщения и кнопки (который обычно открывает диалоговое окно.) Точечный рисунок можно назначить всплывающей подсказки.  
  
 Чтобы включить режим панели сообщения, вызовите [CMFCCaptionBar::Create](#create) и четвертый параметр (bIsMessageBarMode) равен `TRUE`.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCCaptionBar` класса. В примере показано создание элемента управления панели заголовка, задание трехмерной границы заголовка окна, задайте расстояние в пикселях между границей заголовка панели элементов и границей элемента управления заголовка, кнопки для строки заголовка, параметров подсказки для кнопки, задайте текстовую метку для строки заголовка, установки растровое изображение для заголовка окна и в строке заголовка всплывающей подсказки для образа. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#1;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo&#2;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcaptionbar.h  
  
##  <a name="a-namecreatea--cmfccaptionbarcreate"></a><a name="create"></a>CMFCCaptionBar::Create  
 Создает элемент управления панель заголовка и присоединяет его к `CMFCCaptionBar` объекта.  
  
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
 Сочетание логического или стили панели заголовка.  
  
 `pParentWnd`  
 Родительское окно элемента управления заголовка строки.  
  
 `uID`  
 Идентификатор элемента управления заголовка строки.  
  
 `nHeight`  
 Высота в пикселях, заголовок элемента управления. Если это значение -1, высота вычисляется согласно высоту значка, текст и кнопки, которая отображает заголовок панели управления.  
  
 `bIsMessageBarMode`  
 `TRUE`Если заголовок находится в режиме панель сообщений; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если заголовок панели управления создано успешно; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Создании `CMFCCaptionBar` объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `Create` метод, который создает элемент управления Windows и присоединяет его к `CMFCCaptionBar` объекта.  
  
##  <a name="a-namedoesallowdyninsertbeforea--cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore  
 Указывает, может ли другой области динамически вставляются между строки заголовка и его родительского фрейма.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `FALSE` Если не переопределено.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenablebuttona--cmfccaptionbarenablebutton"></a><a name="enablebutton"></a>CMFCCaptionBar::EnableButton  
 Включает или отключает кнопку в заголовке окна.  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить кнопку, `FALSE` для выключения кнопки.  
  
##  <a name="a-namegetalignmenta--cmfccaptionbargetalignment"></a><a name="getalignment"></a>CMFCCaptionBar::GetAlignment  
 Возвращает выравнивание указанного элемента.  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `elem`  
 Элемент заголовка панели для которого необходимо получить выравнивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Выравнивание элемента, таких как кнопки, растровое изображение, текст или значок.  
  
### <a name="remarks"></a>Примечания  
 Выравнивание элемента может принимать одно из следующих значений:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="a-namegetbordersizea--cmfccaptionbargetbordersize"></a><a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize  
 Возвращает размер границы заголовка окна.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в точках границы.  
  
##  <a name="a-namegetbuttonrecta--cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect  
 Возвращает прямоугольник, ограничивающий кнопки в строке заголовка.  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , содержащий координаты ограничивающего прямоугольника кнопки в строке заголовка.  
  
##  <a name="a-namegetmargina--cmfccaptionbargetmargin"></a><a name="getmargin"></a>CMFCCaptionBar::GetMargin  
 Возвращает расстояние между границей заголовка панели элементов и границей элемента управления заголовка строки.  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расстояние в точках между границей заголовка панели элементов и границей элемента управления заголовка строки.  
  
##  <a name="a-nameismessagebarmodea--cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode  
 Указывает, является ли заголовок в режиме панель сообщений.  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если заголовок находится в режиме панель сообщений; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 В режиме панели сообщения заголовок отображает изображение с всплывающей подсказки, текст сообщения и кнопки.  
  
##  <a name="a-namemclrbarbackgrounda--cmfccaptionbarmclrbarbackground"></a><a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground  
 Цвет фона заголовка окна.  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="a-namemclrbarbordera--cmfccaptionbarmclrbarborder"></a><a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder  
 Цвет границы заголовка окна.  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="a-namemclrbartexta--cmfccaptionbarmclrbartext"></a><a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText  
 Цвет текста заголовка строки.  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="a-nameondrawbackgrounda--cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground  
 Вызывается платформой для заполнения фона заголовка окна.  
  
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
 `OnDrawBackground` Метод вызывается, когда заполняется фона заголовка окна. Реализация по умолчанию выполняет заливку фона с помощью [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) цвет.  
  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид заголовка окна.  
  
##  <a name="a-nameondrawbordera--cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder  
 Вызывается платформой для рисования границы заголовка окна.  
  
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
 По умолчанию границы со стилем плоскими.  
  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид границ заголовка окна.  
  
##  <a name="a-nameondrawbuttona--cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton  
 Вызывается платформой для отрисовки кнопки в строке заголовка.  
  
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
 Текст метки кнопки.  
  
 [in] `bEnabled`  
 `TRUE`Если кнопка включена; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид кнопки заголовка окна.  
  
##  <a name="a-nameondrawimagea--cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage  
 Вызывается платформой для рисования изображения панели заголовка.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, который используется для отображения изображения.  
  
 [in] `rect`  
 Указывает ограничивающий прямоугольник изображения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид изображения.  
  
##  <a name="a-nameondrawtexta--cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText  
 Вызывается платформой для рисования текста строки заголовка.  
  
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
  
 Переопределите этот метод в `CMFCCaptionBar` производный класс для настройки внешнего вида текста в строке заголовка.  
  
##  <a name="a-nameremovebitmapa--cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap  
 Удаляет растрового изображения из заголовка окна.  
  
```  
void RemoveBitmap();
```  
  
##  <a name="a-nameremovebuttona--cmfccaptionbarremovebutton"></a><a name="removebutton"></a>CMFCCaptionBar::RemoveButton  
 Удаление кнопки в строке заголовка.  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>Примечания  
 Размещение элементов строки заголовка настраиваются автоматически.  
  
##  <a name="a-nameremoveicona--cmfccaptionbarremoveicon"></a><a name="removeicon"></a>CMFCCaptionBar::RemoveIcon  
 Удаление значка из заголовка окна.  
  
```  
void RemoveIcon();
```  
  
##  <a name="a-nameremovetexta--cmfccaptionbarremovetext"></a><a name="removetext"></a>CMFCCaptionBar::RemoveText  
 Удаляет текстовую метку из заголовка окна.  
  
```  
void RemoveText();
```  
  
##  <a name="a-namesetbitmapa--cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a>CMFCCaptionBar::SetBitmap  
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
 Если `TRUE`, точечный рисунок растягивается, если он не помещается в образе, ограничивающего прямоугольника. В противном случае битовая карта не растягивается.  
  
 [in] `bmpAlignment`  
 Выравнивание изображения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для задания заголовка окна растровое изображение.  
  
 Предыдущие точечного рисунка будет удален автоматически. Если заголовок отображается значок, поскольку вызывается [CMFCCaptionBar::SetIcon](#seticon) метод, точечный рисунок не будет отображаться, пока не будет удален значок путем вызова [CMFCCaptionBar::RemoveIcon](#removeicon).  
  
 Точечный рисунок выравнивается, заданной параметром `bmpAlignment` параметр.  Этот параметр может принимать одно из следующих значений `BarElementAlignment`:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="a-namesetbordersizea--cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize  
 Задает размер границы заголовка окна.  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nSize`  
 Новый размер в точках границы панели заголовка.  
  
##  <a name="a-namesetbuttona--cmfccaptionbarsetbutton"></a><a name="setbutton"></a>CMFCCaptionBar::SetButton  
 Задает кнопку для строки заголовка.  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszLabel`  
 Метка кнопки команд.  
  
 `uiCmdUI`  
 Идентификатор команды кнопки.  
  
 `btnAlignmnet`  
 Выравнивание кнопок.  
  
 `bHasDropDownArrow`  
 `TRUE`Если кнопка отображает стрелку раскрывающегося списка, `FALSE` в противном случае.  
  
##  <a name="a-namesetbuttonpresseda--cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed  
 Указывает, является ли кнопка остается нажатой.  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bPresed`  
 `TRUE`Если кнопки отслеживает его нажатом состоянии `FALSE` в противном случае.  
  
##  <a name="a-namesetbuttontooltipa--cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip  
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
 Подсказка.  
  
##  <a name="a-namesetflatbordera--cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder  
 Задает стиль границы заголовка окна.  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bFlat`  
 `TRUE`Если границы строки заголовка, остается неизменным. `FALSE`Если границы 3D.  
  
##  <a name="a-nameseticona--cmfccaptionbarseticon"></a><a name="seticon"></a>CMFCCaptionBar::SetIcon  
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
 Заголовок панели можно отобразить значки или растровые изображения. В разделе [CMFCCaptionBar::SetBitmap](#setbitmap) чтобы узнать, как отобразить точечный рисунок. Если задать значок и растровое изображение всегда отображается значок. Вызов [CMFCCaptionBar::RemoveIcon](#removeicon) Удаление значка из заголовка окна.  
  
 Значок, выровненный по `iconAlignment` параметр. Он может принимать одно из следующих `BarElementAlignment` значения:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="a-namesetimagetooltipa--cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip  
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
 Подсказка.  
  
##  <a name="a-namesetmargina--cmfccaptionbarsetmargin"></a><a name="setmargin"></a>CMFCCaptionBar::SetMargin  
 Задает расстояние между краем элемента панель заголовка и краем элемента управления заголовка строки.  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nMargin`  
 Расстояние в точках между границей заголовка панели элементов и границей элемента управления заголовка строки.  
  
##  <a name="a-namesettexta--cmfccaptionbarsettext"></a><a name="settext"></a>CMFCCaptionBar::SetText  
 Задает текстовую метку для строки заголовка.  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strText`  
 Чтобы задать строку текста.  
  
 [in] `textAlignment`  
 Выравнивание текста.  
  
### <a name="remarks"></a>Примечания  
 Выравнивание текста метки, заданной параметром `textAlignment` параметр. Он может принимать одно из следующих `BarElementAlignment` значения:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

