---
title: Класс CMFCCaptionButton | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec36bfc82064272e165ea274cd127cc626731643
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368781"
---
# <a name="cmfccaptionbutton-class"></a>Класс CMFCCaptionButton
`CMFCCaptionButton` Класс реализует кнопки, которая отображается в заголовке окна для области закрепления или окна области. Как правило, платформа создает кнопки заголовка автоматически.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="constructors"></a>Конструкторы  
  
|name|Описание|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Создает объект CMFCCaptionButton.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Возвращает команду, представленный кнопки.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|Возвращает идентификатор изображения, связанные с кнопкой.|  
|[CMFCCaptionButton::GetRect](#getrect)|Возвращает прямоугольник, занимаемый кнопки.|  
|[CMFCCaptionButton::GetSize](#getsize)|Возвращает ширину и высоту кнопки.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Указывает, задан ли размер мини-высоте строки заголовка.|  
|[CMFCCaptionButton::Move](#move)|Задает местоположение draw кнопки и Показать состояние окна.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Рисует кнопки заголовка.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Задает размер мини-заголовке.|  
  
## <a name="remarks"></a>Примечания  
 Можно наследовать класс от [класса CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) и использовать защищенный метод `AddButton`, чтобы добавить кнопки заголовка окна мини-рамки.  
  
 CPaneFrameWnd.h определяет идентификаторы команд для двух типов кнопок заголовка:  
  
- `AFX_CAPTION_BTN_PIN`, который отображает кнопку ПИН-код при закрепляемой области поддерживает режим автоматического скрытия.  
  
- `AFX_CAPTION_BTN_CLOSE`, который отображает **закрыть** когда области могут быть закрыты или скрыты.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCCaptionButton` и задайте размер мини-заголовке.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton  
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
 Указывает ли кнопки выравнивается влево.  
  
 В следующей таблице перечислены возможные значения для `nHit` параметра.  
  
|Значение|Команда|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Кнопка закрытия.|  
|`HTMINBUTTON`|Кнопка свертывания.|  
|`HTMAXBUTTON`|Кнопка развертывания окна.|  
|`AFX_HTLEFTBUTTON`|Кнопка со стрелкой влево.|  
|`AFX_HTRIGHTBUTTON`|Кнопка со стрелкой вправо.|  
|`AFX_HTMENU`|Вниз стрелку кнопки меню.|  
|`HTNOWHERE`|Значение по умолчанию; представляет ни одной команды.|  
  
### <a name="remarks"></a>Примечания  
 По умолчанию в заголовке не связаны с командой.  
  
 В заголовке выравниваются на вправо или влево.  
  
##  <a name="gethit"></a>  CMFCCaptionButton::GetHit  
 Возвращает команду, представленный кнопки.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Команда, представленный кнопки.  
  
 В следующей таблице перечислены возможные возвращаемые значения.  
  
|Значение|Команда|  
|-----------|-------------|  
|`AFX_HTCLOSE`|Кнопка закрытия.|  
|`HTMINBUTTON`|Кнопка свертывания.|  
|`HTMAXBUTTON`|Кнопка развертывания окна.|  
|`AFX_HTLEFTBUTTON`|Кнопка со стрелкой влево.|  
|`AFX_HTRIGHTBUTTON`|Кнопка со стрелкой вправо.|  
|`AFX_HTMENU`|Вниз стрелку кнопки меню.|  
|`HTNOWHERE`|Значение по умолчанию; представляет ни одной команды.|  
  
##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID  
 Возвращает идентификатор изображения, связанные с кнопкой.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHorz`  
 `TRUE` Стрелка влево или вправо образа идентификаторы; `FALSE` для вверх или Стрелка вниз изображения идентификаторы.  
  
 [in] `bMaximized`  
 `TRUE` для развертывания образа идентификатора; `FALSE` для свертывания изображения идентификатор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор изображения.  
  
### <a name="remarks"></a>Примечания  
 Параметры указать идентификатор изображения для свернуть или развернуть кнопки заголовка.  
  
##  <a name="getrect"></a>  CMFCCaptionButton::GetRect  
 Возвращает прямоугольник, занимаемый кнопки.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник, представляющий расположение кнопки.  
  
### <a name="remarks"></a>Примечания  
 Если кнопка не видна, возвращаемый размер равен 0.  
  
##  <a name="getsize"></a>  CMFCCaptionButton::GetSize  
 Возвращает ширину и высоту кнопки.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Габариты кнопки.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый размер включает кнопку поля и границы.  
  
##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton  
 Указывает, задан ли размер мини-высоте строки заголовка.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если заголовок равен размеру мини; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="move"></a>  CMFCCaptionButton::Move  
 Задает местоположение draw кнопки и Показать состояние окна.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ptTo`  
 Новое расположение.  
  
 [in] `bHide`  
 Следует ли отображать кнопки.  
  
##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw  
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
 Следует ли рисовать изображения Активная кнопка.  
  
 [in] `bHorz`  
 Зарезервировано для использования в производном классе.  
  
 [in] `bMaximized`  
 Следует ли нарисовать изображение кнопки в развернутом виде.  
  
 [in] `bDisabled`  
 Следует ли рисовать изображения включена кнопка.  
  
### <a name="remarks"></a>Примечания  
 `bMaximized` Параметр используется, когда кнопка находится развернуть или свернуть.  
  
##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton  
 Задает размер мини-заголовке.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 `TRUE` для высоте строки мини-заголовка; `FALSE` для высоте строки заголовка по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)
