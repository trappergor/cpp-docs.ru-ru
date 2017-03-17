---
title: "Класс CMFCToolBarFontSizeComboBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox class
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: 26
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
ms.openlocfilehash: 9dddb563617a708bdc8b2193fa5ee8bd10321828
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarfontsizecombobox-class"></a>Класс CMFCToolBarFontSizeComboBox
Кнопка панели инструментов, который содержит элемент управления ComboBox, позволяющий пользователю выбрать размер шрифта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Создает объект `CMFCToolBarFontSizeComboBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Возвращает размер шрифта, выбранного в твипах.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Заполняет поле со списком всех размеров шрифта, поддерживаемые для указанного шрифта.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Задает размер шрифта в твипах.|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `CMFCToolBarFontSizeComboBox` объекта вместе с [CMFCToolBarFontComboBox класс](../../mfc/reference/cmfctoolbarfontcombobox-class.md) объекта, чтобы позволить пользователю выбрать шрифт и размер шрифта.  
  
 Можно добавить кнопки поле со списком размер шрифта на панели инструментов, так же, как добавить кнопку поле со списком шрифта. Дополнительные сведения см. в разделе [CMFCToolBarFontComboBox класса](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 Когда пользователь выбирает новый шрифт в `CMFCToolBarFontComboBox` объекта, можно заполнить поле со списком размер шрифта поддерживаемые размеры для данного шрифта с помощью [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) метод.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCToolBarFontSizeComboBox` класс для настройки `CMFCToolBarFontSizeComboBox` объекта. В примере, как получить размер шрифта в твипах из текстового поля, заполнить поле со списком размер шрифта все допустимые размеры данный шрифт и размер шрифта в твипах. Этот фрагмент кода является частью [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad №&8;](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 Создает объект `CMFCToolBarFontSizeComboBox`.  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>CMFCToolBarFontSizeComboBox::GetTwipSize  
 Получает размер шрифта в твипах из текстового поля со списком размер шрифта.  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если возвращаемое значение является положительным, это размер шрифта в твипах. Это значение -1, если текстовое поле со списком будет пустым. Это -2, если произошла ошибка.  
  
##  <a name="rebuildfontsizes"></a>CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 Заполняет поле со списком размер шрифта все допустимые размеры данного шрифта.  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] strFontName`  
 Задает имя шрифта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, когда вы хотите синхронизировать между выбор в поле со списком шрифта и поле со списком размер шрифта, такие как [CMFCToolBarFontComboBox класса](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
##  <a name="settwipsize"></a>CMFCToolBarFontSizeComboBox::SetTwipSize  
 Округляет указанный размер (в твипах) до ближайшего размера в точки и затем задает выбранный размер в поле со списком с этим значением.  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nSize`  
 Указывает размер шрифта (в твипах) для установки.  
  
### <a name="remarks"></a>Примечания  
 Далее предыдущий размер шрифтов можно получить, вызвав [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) метод.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Пошаговое руководство: Добавление элементов управления в панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)




