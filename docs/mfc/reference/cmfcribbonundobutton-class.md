---
title: "Класс CMFCRibbonUndoButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton class
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: 35
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
ms.openlocfilehash: d4406e21a7e2a945965020d85a748b93d66b5682
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonundobutton-class"></a>Класс CMFCRibbonUndoButton
`CMFCRibbonUndoButton` Класс реализует кнопку раскрывающегося списка, содержащий последние команды пользователя. Пользователи могут выбрать один или несколько последних команд из раскрывающегося списка, чтобы вернуть или отменить их.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Создает новый `CMFCRibbonUndoButton` объекта, используя идентификатор команды, указать, текстовую метку и изображений из списка изображений родительского объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Добавляет новое действие в списке действий.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Очищает список действий, который представляет раскрывающегося списка.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Определяет количество элементов, которые пользователь выбрал из раскрывающегося списка.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Указывает, содержит ли объект меню.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCRibbonUndoButton` Класс использует стек для представления раскрывающегося списка.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCRibbonUndoButton` и добавьте новое действие в списке действий. Этот фрагмент кода является частью [пример мини-приложения ленты](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction  
 Добавляет новое действие в списке действий.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Метка действия, которое будет отображаться в раскрывающемся списке.  
  
##  <a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList  
 Очищает список действий, который представляет раскрывающегося списка.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 Создает новый `CMFCRibbonUndoButton` объекта, используя идентификатор команды, указать, текстовую метку и изображений из списка изображений родительского объекта.  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Указывает идентификатор команды.  
  
 [in] `lpszText`  
 Задает текст метки кнопки.  
  
 [in] `nSmallImageIndex`  
 Отсчитываемый от нуля индекс в списке изображений родительского объекта небольшое изображение кнопки.  
  
 [in] `nLargeImageIndex`  
 Отсчитываемый от нуля индекс в списке изображений родительский объект для большого изображения кнопки.  
  
 [in] `hIcon`  
 Дескриптор для значка, который можно использовать в качестве изображения кнопки.  
  
##  <a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber  
 Определяет количество элементов, которые пользователь выбрал из раскрывающегося списка.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, которые выбрал пользователь.  
  
##  <a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu  
 Указывает, содержит ли объект меню.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

