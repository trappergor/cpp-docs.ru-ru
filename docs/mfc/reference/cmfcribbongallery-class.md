---
title: "Класс CMFCRibbonGallery | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::AddGroup
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::AddSubItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::Clear
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::EnableMenuResize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::EnableMenuSideBar
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetCompactSize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetDroppedDown
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetGroupName
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetGroupOffset
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetIconsInRow
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetItemToolTip
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetLastSelectedItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetPaletteID
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetRegularSize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetSelectedItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::HasMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsButtonMode
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuResizeEnabled
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuResizeVertical
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuSideBar
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnAfterChangeRect
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnDraw
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnEnable
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnRTLChanged
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::RedrawIcons
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::RemoveItemToolTips
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SelectItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetACCData
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetButtonMode
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetGroupName
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetIconsInRow
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetItemToolTip
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetPaletteID
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnDrawPaletteIcon
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGallery class
ms.assetid: 9734c9c9-981c-4b3f-8c59-264fd41811b4
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c4eadb9820f2d7318131cc4d197dbe28d65491c0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbongallery-class"></a>Класс CMFCRibbonGallery
Реализует коллекции лент в стиле Office 2007.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonGallery : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonGallery::CMFCRibbonGallery](#cmfcribbongallery)|Создает и инициализирует объект `CMFCRibbonGallery`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonGallery::AddGroup](#addgroup)|Добавляет новую группу к коллекции.|  
|[CMFCRibbonGallery::AddSubItem](#addsubitem)|Добавляет новый элемент меню в раскрывающемся меню.|  
|[CMFCRibbonGallery::Clear](#clear)|Удаляет содержимое коллекции.|  
|[CMFCRibbonGallery::EnableMenuResize](#enablemenuresize)|Включает или отключает изменение размера панели меню.|  
|[CMFCRibbonGallery::EnableMenuSideBar](#enablemenusidebar)|Включает или отключает боковой панели в левом меню.|  
|[CMFCRibbonGallery::GetCompactSize](#getcompactsize)|(Переопределяет [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonGallery::GetDroppedDown](#getdroppeddown)|(Переопределяет [CMFCRibbonBaseElement::GetDroppedDown](../../mfc/reference/cmfcribbonbaseelement-class.md#getdroppeddown).)|  
|[CMFCRibbonGallery::GetGroupName](#getgroupname)|Возвращает имя группы, расположенный по указанному индексу.|  
|[CMFCRibbonGallery::GetGroupOffset](#getgroupoffset)||  
|[CMFCRibbonGallery::GetIconsInRow](#geticonsinrow)|Возвращает количество элементов в строке коллекции ленты.|  
|[CMFCRibbonGallery::GetItemToolTip](#getitemtooltip)|Возвращает текст подсказки, связанный с элементом в коллекции.|  
|[CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem)|Возвращает индекс последнего элемента в коллекции, который выбрал пользователь.|  
|[CMFCRibbonGallery::GetPaletteID](#getpaletteid)|Возвращает идентификатор команды в текущей коллекции.|  
|[CMFCRibbonGallery::GetRegularSize](#getregularsize)|(Переопределяет [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonGallery::GetSelectedItem](#getselecteditem)||  
|[CMFCRibbonGallery::HasMenu](#hasmenu)|(Переопределяет [CMFCRibbonButton::HasMenu](../../mfc/reference/cmfcribbonbutton-class.md#hasmenu).)|  
|[CMFCRibbonGallery::IsButtonMode](#isbuttonmode)|Указывает, содержится ли в коллекции кнопки коллекции.|  
|[CMFCRibbonGallery::IsMenuResizeEnabled](#ismenuresizeenabled)|Указывает ли изменение размеров меню является включены или отключены.|  
|[CMFCRibbonGallery::IsMenuResizeVertical](#ismenuresizevertical)||  
|[CMFCRibbonGallery::IsMenuSideBar](#ismenusidebar)|Указывает, включен ли на боковой панели.|  
|[CMFCRibbonGallery::OnAfterChangeRect](#onafterchangerect)|(Переопределяет `CMFCRibbonButton::OnAfterChangeRect`.)|  
|[CMFCRibbonGallery::OnDraw](#ondraw)|(Переопределяет [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonGallery::OnEnable](#onenable)|(Переопределяет `CMFCRibbonBaseElement::OnEnable`.)|  
|[CMFCRibbonGallery::OnRTLChanged](#onrtlchanged)|(Переопределяет [CMFCRibbonBaseElement::OnRTLChanged](../../mfc/reference/cmfcribbonbaseelement-class.md#onrtlchanged).)|  
|[CMFCRibbonGallery::RedrawIcons](#redrawicons)|Перерисовывает коллекции.|  
|[CMFCRibbonGallery::RemoveItemToolTips](#removeitemtooltips)|Удаляет всплывающие подсказки из всех элементов в коллекции.|  
|[CMFCRibbonGallery::SelectItem](#selectitem)||  
|[CMFCRibbonGallery::SetACCData](#setaccdata)|(Переопределяет [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
|[CMFCRibbonGallery::SetButtonMode](#setbuttonmode)|Включение отображения ленты коллекции как кнопку раскрывающегося списка или палитры непосредственно на ленте.|  
|[CMFCRibbonGallery::SetGroupName](#setgroupname)|Задает имя группы.|  
|[CMFCRibbonGallery::SetIconsInRow](#seticonsinrow)|Определяет количество элементов для строки в коллекции.|  
|[CMFCRibbonGallery::SetItemToolTip](#setitemtooltip)|Задает текст подсказки для элемента в коллекции.|  
|[CMFCRibbonGallery::SetPalette](#setpalette)|Присоединяет палитры Галерея на ленте.|  
|[CMFCRibbonGallery::SetPaletteID](#setpaletteid)|Определяет идентификатор команды, который отправляется в `WM_COMMAND` сообщений, если был выбран элемент коллекции.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonGallery::OnDrawPaletteIcon](#ondrawpaletteicon)|Вызывается инфраструктурой при рисовании значок в виде коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Кнопка коллекции ведет себя подобно регулярных меню кнопки, за исключением того, что коллекция отображается, когда пользователь открывает его. При выборе элемента в коллекции платформа отправляет `WM_COMMAND` сообщения, а также идентификатор команды кнопки. После обработки сообщения, следует вызвать [CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem) для определения, какой элемент был выбран из коллекции.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCRibbonGallery` класс для настройки `CMFCRibbonGallery` объекта. В примере показано, как указать число элементов для строки в коллекции, включить изменение размера панели меню, на боковой панели слева от всплывающего меню и отображения галереи ленты как палитра непосредственно на ленте. Этот фрагмент кода является частью [пример рисования клиента](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient №&6;](../../mfc/reference/codesnippet/cpp/cmfcribbongallery-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonPaletteGallery.h  
  
##  <a name="addgroup"></a>CMFCRibbonGallery::AddGroup  
 Добавляет новую группу к коллекции.  
  
```  
void AddGroup(
    LPCTSTR lpszGroupName,  
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    CMFCToolBarImages& imagesGroup);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    int nIconsNum);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszGroupName`  
 Задает имя группы.  
  
 [in] `uiImagesPaletteResID`  
 Указывает идентификатор ресурса для списка изображений, которое содержит изображения для группы.  
  
 [in] `cxPaletteImage`  
 Задает ширину в пикселях изображения.  
  
 [in] `imagesGroup`  
 Ссылка на список изображений, содержащий группы образов.  
  
 [in] `nIconsNum`  
 Указывает количество значков в группе. Этот параметр должен быть задан только для пользовательских (рисование владельцем) группы.  
  
### <a name="remarks"></a>Примечания  
 Элементы в коллекции ленты можно разделить на несколько групп путем вызова данного метода. Каждая группа может иметь заголовок.  
  
##  <a name="addsubitem"></a>CMFCRibbonGallery::AddSubItem  
 Добавляет новый элемент меню в раскрывающемся меню.  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1,  
    BOOL bOnTop=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pSubItem`  
 Указатель на элемент, добавляемый в меню.  
  
 [in] `nIndex`  
 Расположение отсчитываемый от нуля индекс места вставки элемента.  
  
 [in] `bOnTop`  
 `TRUE`Чтобы указать, что элемента должны быть вставлены перед коллекции ленты; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Всплывающее окно галереи можно объединить с помощью элементов всплывающих меню путем вызова данного метода. Пункты меню можно разместить до или после коллекции.  
  
 Чтобы вставить элемент до коллекции, установите `bOnTop` в `TRUE`. Задайте `bOnTop` для `FALSE` для вставки элемента ниже коллекции.  
  
> [!NOTE]
>  Параметр `nIndex` указывает индекс вставки в верхней части галереи, а также в нижней части галереи. Например, если вам нужно вставить элемент на одну позицию перед коллекции, установить `nIndex` 1 и `bOnTop` в `TRUE`. Аналогичным образом, если вам нужно вставить элемент на одну позицию ниже коллекции, настроить `nIndex` 1 и `bOnTop` в `FALSE`.  
  
##  <a name="clear"></a>CMFCRibbonGallery::Clear  
 Удаляет содержимое коллекции.  
  
```  
virtual void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы удалить все содержимое из коллекции ленты. Это необходимо сделать перед присоединением новой коллекции ленты или набор групп в коллекции ленты.  
  
##  <a name="cmfcribbongallery"></a>CMFCRibbonGallery::CMFCRibbonGallery  
 Создает и инициализирует [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md) объекта.  
  
```  
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CMFCToolBarImages& imagesPalette);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    UINT uiImagesPaletteResID=0,  
    int cxPaletteImage=0);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CSize sizeIcon,  
    int nIconsNum,  
    BOOL bDefaultButtonStyle=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Указывает идентификатор команды команда выполняется, когда пользователь нажимает кнопку.  
  
 `lpszText`  
 Задает текст, отображаемый на кнопке.  
  
 `nSmallImageIndex`  
 Отсчитываемый от нуля индекс небольшое изображение для отображения на кнопке.  
  
 `nLargeImageIndex`  
 Отсчитываемый от нуля индекс большое изображение для отображения на кнопке.  
  
 `imagesPalette`  
 Ссылку на [CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) объект, который содержит изображения для отображения в коллекции.  
  
 `uiImagesPaletteResID`  
 Идентификатор ресурса из списка изображений для отображения в коллекции.  
  
 `cxPaletteImage`  
 Ширина в точках изображения в коллекции.  
  
 `sizeIcon`  
 Размер в пикселях образа из коллекции.  
  
 `nIconsNum`  
 Указывает количество значков в галерее.  
  
 `bDefaultButtonStyle`  
 Указывает, следует ли использовать значение по умолчанию или стиль кнопки пользователем.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablemenuresize"></a>CMFCRibbonGallery::EnableMenuResize  
 Включает или отключает изменение размера панели меню.  
  
```  
void EnableMenuResize(
    BOOL bEnable = TRUE,  
    BOOL bVertcalOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить изменение размеров меню; в противном случае — `FALSE`.  
  
 [in] `bVertcalOnly`  
 `TRUE`Чтобы указать, что коллекции может быть изменен только по вертикали; `FALSE` для указания, что коллекции могут быть изменения размера и по вертикали и по горизонтали.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы включить или отключить изменение размеров ленты коллекции. При включении изменение размеров ленты коллекции отображает захвата, пользователь может использовать для изменения размера.  
  
##  <a name="enablemenusidebar"></a>CMFCRibbonGallery::EnableMenuSideBar  
 Включает или отключает боковой панели в левом меню.  
  
```  
void EnablMenuSideBar(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы указать, что включен на боковой панели; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для включения или отключения Office XP в стиле боковой панели в левой части меню.  
  
##  <a name="getcompactsize"></a>CMFCRibbonGallery::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdroppeddown"></a>CMFCRibbonGallery::GetDroppedDown  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getgroupname"></a>CMFCRibbonGallery::GetGroupName  
 Возвращает имя группы, расположенный по указанному индексу.  
  
```  
LPCTSTR GetGroupName(int nGroupIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroupIndex`  
 Задает отсчитываемый от нуля индекс для группы, имя которого требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя группы, расположенный по указанному индексу. Передача недопустимый индекс приведет к ошибочного утверждения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getgroupoffset"></a>CMFCRibbonGallery::GetGroupOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetGroupOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="geticonsinrow"></a>CMFCRibbonGallery::GetIconsInRow  
 Возвращает количество элементов в строке коллекции ленты.  
  
```  
int GetIconsInRow() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в строке.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemtooltip"></a>CMFCRibbonGallery::GetItemToolTip  
 Возвращает текст подсказки, связанный с элементом в коллекции.  
  
```  
LPCTSTR GetItemToolTip(int nItemIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nItemIndex`  
 Задает отсчитываемый от нуля индекс элемента, для которого требуется извлечь текст всплывающей подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку всплывающей подсказки, присвоенное элементу в коллекции ленты. Он может быть `NULL` подсказка назначается этому элементу.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlastselecteditem"></a>CMFCRibbonGallery::GetLastSelectedItem  
 Возвращает индекс последнего элемента в коллекции ленты, выбранный пользователем.  
  
```  
static int GetLastSelectedItem(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Указывает идентификатор команды меню элемента, который открыт коллекции ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При выборе любого элемента в коллекции ленты, отправляет библиотеку `WM_COMMAND` сообщение, а также идентификатор команды кнопки меню, открыть галерею ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpaletteid"></a>CMFCRibbonGallery::GetPaletteID  
 Возвращает идентификатор текущей палитры.  
  
```  
int GetPaletteID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды выбранного палитры.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getregularsize"></a>CMFCRibbonGallery::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getselecteditem"></a>CMFCRibbonGallery::GetSelectedItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasmenu"></a>CMFCRibbonGallery::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isbuttonmode"></a>CMFCRibbonGallery::IsButtonMode  
 Указывает, содержится ли в коллекции кнопки палитры.  
  
```  
BOOL IsButtonMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если палитра отображается в виде кнопки раскрывающегося меню; `FALSE` Если палитре отображается непосредственно на ленте.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ismenuresizeenabled"></a>CMFCRibbonGallery::IsMenuResizeEnabled  
 Указывает, включена ли изменение размеров меню.  
  
```  
BOOL IsMenuResizeEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если изменение размеров меню включен; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ismenuresizevertical"></a>CMFCRibbonGallery::IsMenuResizeVertical  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuResizeVertical() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ismenusidebar"></a>CMFCRibbonGallery::IsMenuSideBar  
 Указывает, включен ли на боковой панели.  
  
```  
BOOL IsMenuSideBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если на боковой панели Office XP в стиле рисуется с левой стороны меню; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onafterchangerect"></a>CMFCRibbonGallery::OnAfterChangeRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>CMFCRibbonGallery::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawpaletteicon"></a>CMFCRibbonGallery::OnDrawPaletteIcon  
 Вызывается инфраструктурой при рисовании значок в виде коллекции.  
  
```  
virtual void OnDrawPaletteIcon(
    CDC* pDC,  
    CRect rectIcon,  
    int nIconIndex,  
    CMFCRibbonGalleryIcon* pIcon,  
    COLORREF clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, используемого для рисования.  
  
 [in] `rectIcon`  
 Указывает ограничивающий прямоугольник значка для рисования.  
  
 [in] `nIconIndex`  
 Задает отсчитываемый от нуля индекс в списке изображений значков коллекции значка для рисования.  
  
 [in] `pIcon`  
 Указатель на значок рисуемой.  
  
 [in] `clrText`  
 Задает цвет для текста элемента для рисования.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод в производном классе, чтобы настроить внешний вид Галерея на ленте.  
  
##  <a name="onenable"></a>CMFCRibbonGallery::OnEnable  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onrtlchanged"></a>CMFCRibbonGallery::OnRTLChanged  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="redrawicons"></a>CMFCRibbonGallery::RedrawIcons  
 Перерисовывает коллекции.  
  
```  
void RedrawIcons();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для повторной отрисовки коллекции. Этот метод необходимо вызывать при изменении содержимого коллекции во время выполнения.  
  
##  <a name="removeitemtooltips"></a>CMFCRibbonGallery::RemoveItemToolTips  
 Удаляет всплывающие подсказки из всех элементов в коллекции.  
  
```  
void RemoveItemToolTips();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="selectitem"></a>CMFCRibbonGallery::SelectItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SelectItem(int nItemIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nItemIndex`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setaccdata"></a>CMFCRibbonGallery::SetACCData  
 Заполняет указанный объект `CAccessibilityData` , используя данные специальных возможностей из галереи ленты.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,   
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
 Родительское окно окна галереи ленты.  
  
 [выходной] `data`  
 Объект `CAccessibilityData` , получающий данные специальных возможностей из галереи ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Значение `TRUE`, если метод выполнен успешно; в противном случае — значение `FALSE`.  
  
##  <a name="setbuttonmode"></a>CMFCRibbonGallery::SetButtonMode  
 Задает режим отображения галереи ленты, как кнопка раскрывающегося списка или палитры непосредственно на ленте.  
  
```  
void SetButtonMode(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 `TRUE`для отображения галереи ленты в виде кнопки раскрывающегося меню; `FALSE` для отображения содержимого коллекции ленты непосредственно на ленте.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setgroupname"></a>CMFCRibbonGallery::SetGroupName  
 Задает имя группы.  
  
```  
void SetGroupName(
    int nGroupIndex,  
    LPCTSTR lpszGroupName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGroupIndex`  
 Задает отсчитываемый от нуля индекс, для которого изменяется имя группы.  
  
 [in] `lpszGroupName`  
 Указывает новое имя для группы.  
  
### <a name="remarks"></a>Примечания  
 Группы, имя которого изменяется должно быть добавлено с помощью [CMFCRibbonGallery::AddGroup](#addgroup) метод.  
  
##  <a name="seticonsinrow"></a>CMFCRibbonGallery::SetIconsInRow  
 Задает количество элементов на каждую строку из коллекции.  
  
```  
void SetIconsInRow(int nIconsInRow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIconsInRow`  
 Указывает количество элементов в каждой строке коллекции.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для указания ширины коллекции ленты.  
  
##  <a name="setitemtooltip"></a>CMFCRibbonGallery::SetItemToolTip  
 Задает текст подсказки для элемента в коллекции.  
  
```  
void SetItemToolTip(
    int nItemIndex,  
    LPCTSTR lpszToolTip);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nItemIndex`  
 Отсчитываемый от нуля индекс элемента палитры, с которым связывается всплывающей подсказки.  
  
 [in] `lpszToolTip`  
 Текст, отображаемый на подсказке.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpalette"></a>CMFCRibbonGallery::SetPalette  
 Присоединяет палитры Галерея на ленте.  
  
```  
void SetPalette(CMFCToolBarImages& imagesPalette);

 
void SetPalette(
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `imagesPalette`  
 Задает список изображений, содержащий значки, которые появляются в коллекции.  
  
 [in] `uiImagesPaletteResID`  
 Указывает идентификатор ресурса список изображений, содержащий значки, которые появляются в коллекции.  
  
 [in] `cxPaletteImage`  
 Ширина в пикселях изображения в коллекции.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpaletteid"></a>CMFCRibbonGallery::SetPaletteID  
 Определяет идентификатор команды, который отправляется в **WM_COMMAND** сообщений, если пользователь выбирает элемент коллекции.  
  
```  
void SetPaletteID(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Указывает идентификатор команды, который отправляется в **WM_COMMAND** сообщений, если пользователь выбирает элемент коллекции.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить конкретного элемента, выбранного пользователем из коллекции, вызовите [CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem) статический метод.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Класс CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

