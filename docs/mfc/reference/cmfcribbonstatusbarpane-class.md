---
title: "Класс CMFCRibbonStatusBarPane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCRibbonStatusBarPane class
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
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
ms.openlocfilehash: a101e50f55efab44e4cb66d314b2426228dbc5c0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbarpane-class"></a>Класс CMFCRibbonStatusBarPane
`CMFCRibbonStatusBarPane` Класс реализует элемент ленты, можно добавить в строку состояния ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Создает и инициализирует объект `CMFCRibbonStatusBarPane`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Возвращает строку, которая определяет длинной строку текста, который может быть отображен в области без усечения.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Возвращает текущее значение выравнивания текста.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Определяет, является ли анимация в данный момент.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Определяет, находится ли область в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Переопределяет [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Переопределяет [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Определяет наибольший строку текста, который может быть отображен в области без усечения.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Назначает области списка изображений, который может использоваться для анимации.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Задает выравнивание текста.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Запускает анимацию, назначенный для области.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Останавливает анимацию, назначенный для области. .|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Вызывается инфраструктурой при остановке анимации, назначенные области.|  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных методов класса `CMFCRibbonStatusBarPane`. В примере показано `CMFCRibbonStatusBarPane` объекта, задать выравнивание текста метки панели строки состояния, определить самую длинную строку текста, могут отображаться в панели строки состояния без усечения, присоединение к панели строки состояния списка изображений, который можно использовать для анимации и начала анимации.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Создайте объект панели в строке состояния.  
  
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
 Если `TRUE`, области «состояние» не может быть выделен или выбран, щелкнув его.  
  
 [in] `hIcon`  
 Указывает дескриптор значка, отображаемого в области.  
  
 [in] `lpszAlmostLargeText`  
 Указывает самая длинная текстовая строка, может отображаться в области.  
  
 [in] `hBmpAnimationList`  
 Указывает дескриптор списка изображений, который используется для анимации.  
  
 [in] `cxAnimation`  
 Ширина в пикселях значка в списке изображений, который используется для анимации.  
  
 [in] `clrTrnsp`  
 Указывает прозрачный цвет изображения в списке изображений, которые используются для анимации.  
  
 [in] `uiAnimationListResID`  
 Указывает идентификатор ресурса из списка изображений, который используется для анимации.  
  
##  <a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Возвращает наибольший текстовую строку для отображения панели строки состояния.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Самая длинная текстовая строка для отображения панели строки состояния.  
  
##  <a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign  
 Возвращает текущее значение выравнивания текста метки панели строки состояния.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее выравнивание текста, может принимать одно из следующих действий:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation  
 Определяет, является ли анимация в данный момент.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если анимация выполняется; `FALSE` в противном случае.  
  
##  <a name="isextended"></a>CMFCRibbonStatusBarPane::IsExtended  
 Определите, находится ли область в расширенной области строки состояния ленты.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область находится на строке расширенной области состояния. В противном случае — значение `FALSE`.  
  
##  <a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CDC*`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation  
 Платформа вызывает этот метод при завершении анимации, назначенные области.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Примечания  
 `StopAnimation`вызовы метода `OnFinishAnimation` метод, который можно использовать для очистки данных при завершении анимации.  
  
##  <a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Определите самую длинную строку текста, который может быть отображен в панели строки состояния без усечения.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszAlmostLargeText`  
 Указывает, максимальная длина строки, которые могут отображаться на панели строки состояния без усечения.  
  
### <a name="remarks"></a>Примечания  
 Библиотека вычисляет размер текста, `lpszAlmostLargeText` указывает и соответствующим образом изменяет размер панели. Текст усекается, если он еще не помещается в области.  
  
##  <a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList  
 Присоединяет к панели строки состояния списка изображений, который может использоваться для анимации.  
  
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
 Указывает дескриптор списка изображений.  
  
 [in] `cxAnimation`  
 Ширина в пикселях кадра, в списке изображений.  
  
 [in] `clrTransp`  
 Указывает прозрачный цвет из списка изображений.  
  
 [in] `uiAnimationListResID`  
 Указывает идентификатор ресурса для списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если список изображений успешно подключился к панели строки состояния; `FALSE` в противном случае.  
  
##  <a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign  
 Задает выравнивание текста метки панели строки состояния.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nAlign`  
 Задает выравнивание текста.  
  
### <a name="remarks"></a>Примечания  
 `nAlign`может принимать одно из следующих значений:  
  
- `TA_LEFT`: левому краю  
  
- `TA_CENTER:`Выравнивание по центру  
  
- `TA_RIGHT:`Выравнивание по правому краю  
  
##  <a name="startanimation"></a>CMFCRibbonStatusBarPane::StartAnimation  
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
 Указывает, сколько для воспроизведения анимации, в миллисекундах. Используйте значение -1 для бесконечного цикла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо указать дескриптор списка изображений, перед вызовом метода `StartAnimation` с помощью `SetAnimationList`.  
  
##  <a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation  
 Останавливает анимации, который назначен панели строки состояния.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Класс CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

