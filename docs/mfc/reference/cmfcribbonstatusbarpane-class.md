---
title: Класс CMFCRibbonStatusBarPane | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df9109ef4613a2fb905fc5bef525f3553155417b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonstatusbarpane-class"></a>Класс CMFCRibbonStatusBarPane
`CMFCRibbonStatusBarPane` Класс реализует элемент ленты, можно добавить в строку статуса ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Создает и инициализирует объект `CMFCRibbonStatusBarPane`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Возвращает строку, которая определяет длинного строку текста, который может быть отображен в области без усечения.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Возвращает текущее значение выравнивания текста.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Определяет, является ли анимация хода выполнения.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Определяет, находится ли область в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Переопределяет [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Переопределяет [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Определяет, максимальная длина строки текст, который может быть отображен в области без усечения.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Назначает области списка изображений, который можно использовать для анимации.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Задает выравнивание текста.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Запуск анимации, которая назначается на панель.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Останавливает анимации, которая назначается на панель. .|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Вызывается платформой при остановке анимации, которая назначается на панель.|  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных методов класса `CMFCRibbonStatusBarPane`. В примере показано `CMFCRibbonStatusBarPane` объекта, задать выравнивание текста метки панели строки состояния, определения длинного текста, могут быть отображены в панели строки состояния без усечения, подключения к панели строки состояния, можно использовать для списка изображений Анимация и начала анимации.  
  
 [!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>  CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Создание объекта панели в строке состояния.  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nCmdID`  
 Указывает идентификатор области.  
  
 [in] `lpszText`  
 Задает текстовую строку для отображения на панели.  
  
 [in] `bIsStatic`  
 Если `TRUE`, панель состояния нельзя выделяются или выбрать, щелкнув его.  
  
 [in] `hIcon`  
 Указывает дескриптор значка, отображаемого на панели.  
  
 [in] `lpszAlmostLargeText`  
 Указывает, максимальная длина строки текста, отображаемой области.  
  
 [in] `hBmpAnimationList`  
 Задает дескриптор для списка изображений, используемое для анимации.  
  
 [in] `cxAnimation`  
 Ширина в пикселях значка в списке изображений, который используется для анимации.  
  
 [in] `clrTrnsp`  
 Указывает прозрачный цвет изображения в списке изображений, которые используются для анимации.  
  
 [in] `uiAnimationListResID`  
 Указывает идентификатор ресурса из списка изображений, используемое для анимации.  
  
##  <a name="getalmostlargetext"></a>  CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Возвращает Максимальная длина строки текста для отображения панели строки состояния.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная длина строки текста для отображения панели строки состояния.  
  
##  <a name="gettextalign"></a>  CMFCRibbonStatusBarPane::GetTextAlign  
 Возвращает текущее значение параметра Выравнивание текста метки панели строки состояния.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее выравнивание текста, может принимать одно из следующих действий:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="isanimation"></a>  CMFCRibbonStatusBarPane::IsAnimation  
 Определяет, является ли анимация хода выполнения.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если анимация выполняется; `FALSE` в противном случае.  
  
##  <a name="isextended"></a>  CMFCRibbonStatusBarPane::IsExtended  
 Определите, находится ли область в расширенной области строки состояния ленты.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если панель строки расширенной области состояния. В противном случае — значение `FALSE`.  
  
##  <a name="ondrawborder"></a>  CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CDC*`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onfillbackground"></a>  CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onfinishanimation"></a>  CMFCRibbonStatusBarPane::OnFinishAnimation  
 Этот метод вызывается платформой при завершении анимации, которая назначается на панель.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Примечания  
 `StopAnimation` вызовы метода `OnFinishAnimation` метод, который можно использовать для очистки данных после окончания анимации.  
  
##  <a name="setalmostlargetext"></a>  CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Определите длинную строку текста, который может быть отображен в панели строки состояния без усечения.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszAlmostLargeText`  
 Указывает, максимальная длина строки, которые могут отображаться на панели строки состояния без усечения.  
  
### <a name="remarks"></a>Примечания  
 Библиотека вычисляет размер текста, `lpszAlmostLargeText` указывает и соответствующим образом изменяет размер панели. Текст усекается, если он по-прежнему не умещается в области.  
  
##  <a name="setanimationlist"></a>  CMFCRibbonStatusBarPane::SetAnimationList  
 Присоединяет панели строки состояния списка изображений, который можно использовать для анимации.  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hBmpAnimationList`  
 Задает дескриптор для списка изображений.  
  
 [in] `cxAnimation`  
 Ширина в пикселях кадра, в списке изображений.  
  
 [in] `clrTransp`  
 Указывает прозрачный цвет из списка изображений.  
  
 [in] `uiAnimationListResID`  
 Указывает идентификатор ресурса для списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если список изображений успешно подключился к панели строки состояния; `FALSE` в противном случае.  
  
##  <a name="settextalign"></a>  CMFCRibbonStatusBarPane::SetTextAlign  
 Задает выравнивание текста метки панели строки состояния.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nAlign`  
 Задает выравнивание текста.  
  
### <a name="remarks"></a>Примечания  
 `nAlign` Может принимать одно из следующих значений:  
  
- `TA_LEFT`: левому краю  
  
- `TA_CENTER:` Выравнивание по центру  
  
- `TA_RIGHT:` Выравнивание по правому краю  
  
##  <a name="startanimation"></a>  CMFCRibbonStatusBarPane::StartAnimation  
 Запуск анимации, которые назначены области.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nFrameDelay`  
 Указывает частоту кадров анимации, в миллисекундах.  
  
 [in] `nDuration`  
 Определяет, как долго для воспроизведения анимации, в миллисекундах. Используйте значение -1 для бесконечный цикл.  
  
### <a name="remarks"></a>Примечания  
 Необходимо указать дескриптор для списка изображений, перед вызовом метода `StartAnimation` с помощью `SetAnimationList`.  
  
##  <a name="stopanimation"></a>  CMFCRibbonStatusBarPane::StopAnimation  
 Останавливает анимации, которая назначена панели строки состояния.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Класс CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)
