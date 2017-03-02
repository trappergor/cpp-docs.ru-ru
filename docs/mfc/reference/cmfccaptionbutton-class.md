---
title: "Класс CMFCCaptionButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton class
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
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
ms.openlocfilehash: 9d6342f87622c34b671ad5ea443eb78ffd8c3838
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccaptionbutton-class"></a>Класс CMFCCaptionButton
`CMFCCaptionButton` Класс реализует кнопку, которая отображается в заголовке окна для закрепляемой области или окна области. Как правило, платформа создает кнопки заголовка автоматически.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Создает объект CMFCCaptionButton.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Возвращает команду, представленного кнопки.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|Возвращает идентификатор изображения, связанные с кнопкой.|  
|[CMFCCaptionButton::GetRect](#getrect)|Возвращает прямоугольник, занимаемый кнопки.|  
|[CMFCCaptionButton::GetSize](#getsize)|Возвращает ширину и высоту кнопки.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Указывает, установлен ли размер мини-высоте строки заголовка.|  
|[CMFCCaptionButton::Move](#move)|Задает местоположение рисования кнопку и показ состояния окна.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Рисует кнопки заголовка.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Задает размер мини-заголовке.|  
  
## <a name="remarks"></a>Примечания  
 Можно наследовать класс от [класса CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) и использовать защищенный метод `AddButton`, для добавления кнопки заголовка окна мини-кадра.  
  
 CPaneFrameWnd.h определяет идентификаторы команд для двух типов значков в заголовке:  
  
- `AFX_CAPTION_BTN_PIN`, которая отображает кнопку закрепления при закрепляемой области поддерживает режим автоматического скрытия.  
  
- `AFX_CAPTION_BTN_CLOSE`, который отображает **закрыть** когда области могут быть закрыты или скрыты.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCCaptionButton` и задайте размер мини-заголовке.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#43;](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcaptionbutton.h  
  
##  <a name="a-namecmfccaptionbuttona--cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a>CMFCCaptionButton::CMFCCaptionButton  
 Создает объект `CMFCCaptionButton`.  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHit`  
 Команда, назначенная данной кнопке.  
  
 [in] `bLeftAlign`  
 Указывает, выравнивается ли кнопка слева.  
  
 В следующей таблице перечислены возможные значения для `nHit` параметр.  
  
|Значение|Команда|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Кнопка закрытия.|  
|`HTMINBUTTON`|Кнопка свертывания.|  
|`HTMAXBUTTON`|Кнопка развертывания окна.|  
|`AFX_HTLEFTBUTTON`|Кнопка со стрелкой влево.|  
|`AFX_HTRIGHTBUTTON`|Кнопка со стрелкой вправо.|  
|`AFX_HTMENU`|Меню клавишу со стрелкой.|  
|`HTNOWHERE`|Значение по умолчанию; представляет ни одной команды.|  
  
### <a name="remarks"></a>Примечания  
 По умолчанию кнопки заголовка не связаны с командой.  
  
 Кнопки заголовка выравнивается по правой или левой.  
  
##  <a name="a-namegethita--cmfccaptionbuttongethit"></a><a name="gethit"></a>CMFCCaptionButton::GetHit  
 Возвращает команду, представленного кнопки.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Команда, представленного кнопки.  
  
 В следующей таблице перечислены возможные возвращаемые значения.  
  
|Значение|Команда|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Кнопка закрытия.|  
|`HTMINBUTTON`|Кнопка свертывания.|  
|`HTMAXBUTTON`|Кнопка развертывания окна.|  
|`AFX_HTLEFTBUTTON`|Кнопка со стрелкой влево.|  
|`AFX_HTRIGHTBUTTON`|Кнопка со стрелкой вправо.|  
|`AFX_HTMENU`|Меню клавишу со стрелкой.|  
|`HTNOWHERE`|Значение по умолчанию; представляет ни одной команды.|  
  
##  <a name="a-namegeticonida--cmfccaptionbuttongeticonid"></a><a name="geticonid"></a>CMFCCaptionButton::GetIconID  
 Возвращает идентификатор изображения, связанные с кнопкой.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHorz`  
 `TRUE`Стрелка влево или вправо образа идентификаторы; `FALSE` для вверх или Стрелка вниз изображения идентификаторы.  
  
 [in] `bMaximized`  
 `TRUE`для идентификатора развернуть образ; `FALSE` для свертывания изображения идентификатор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор изображения.  
  
### <a name="remarks"></a>Примечания  
 Параметры укажите идентификаторы изображение свернуть или развернуть кнопки заголовка.  
  
##  <a name="a-namegetrecta--cmfccaptionbuttongetrect"></a><a name="getrect"></a>CMFCCaptionButton::GetRect  
 Возвращает прямоугольник, занимаемый кнопки.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник, представляющий расположение кнопки.  
  
### <a name="remarks"></a>Примечания  
 Если кнопка не видна, возвращаемый размер равен 0.  
  
##  <a name="a-namegetsizea--cmfccaptionbuttongetsize"></a><a name="getsize"></a>CMFCCaptionButton::GetSize  
 Возвращает ширину и высоту кнопки.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Габаритные размеры кнопки.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый размер включает кнопку поля и границы.  
  
##  <a name="a-nameisminiframebuttona--cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a>CMFCCaptionButton::IsMiniFrameButton  
 Указывает, установлен ли размер мини-высоте строки заголовка.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если заголовок равен размеру мини; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemovea--cmfccaptionbuttonmove"></a><a name="move"></a>CMFCCaptionButton::Move  
 Задает местоположение рисования кнопку и показ состояния окна.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ptTo`  
 Новое расположение.  
  
 [in] `bHide`  
 Следует ли показывать кнопку.  
  
##  <a name="a-nameondrawa--cmfccaptionbuttonondraw"></a><a name="ondraw"></a>CMFCCaptionButton::OnDraw  
 Рисует кнопки заголовка.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для кнопки.  
  
 [in] `bActive`  
 Следует ли Рисование изображения активной кнопки.  
  
 [in] `bHorz`  
 Зарезервировано для использования в производном классе.  
  
 [in] `bMaximized`  
 Следует ли рисовать изображение развернутого кнопки.  
  
 [in] `bDisabled`  
 Следует ли рисовать включена кнопка изображения.  
  
### <a name="remarks"></a>Примечания  
 `bMaximized` Параметр используется, когда кнопка находится развернуть или свернуть.  
  
##  <a name="a-namesetminiframebuttona--cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a>CMFCCaptionButton::SetMiniFrameButton  
 Задает размер мини-заголовке.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 `TRUE`для высоты мини-заголовок панели; `FALSE` для высоте строки заголовка по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)

