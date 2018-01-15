---
title: "Класс CMFCToolBarFontSizeComboBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6ba8dde4142cff3606cc2b5ad1861096637f68c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>Класс CMFCToolBarFontSizeComboBox
Кнопка панели инструментов, который содержит поле со списком, позволяющий пользователю выбрать размер шрифта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Создает объект `CMFCToolBarFontSizeComboBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Возвращает размер шрифта, выбранного в твипах.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Заполняет поле со списком всех размеров поддерживаемых шрифта выбранного шрифта.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Задает размер шрифта в твипах.|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `CMFCToolBarFontSizeComboBox` объекта вместе с [CMFCToolBarFontComboBox класс](../../mfc/reference/cmfctoolbarfontcombobox-class.md) объекта, чтобы пользователь мог выбрать шрифт и размер шрифта.  
  
 Можно добавить кнопки поля со списком размер шрифта на панели инструментов, так же, как добавить кнопки поля со списком шрифтов. Дополнительные сведения см. в разделе [CMFCToolBarFontComboBox класса](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 Когда пользователь выбирает новый шрифт в `CMFCToolBarFontComboBox` объекта, можно заполнить поле со списком размер шрифта поддерживаемые размеры для данного шрифта с помощью [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) метод.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCToolBarFontSizeComboBox` класса, чтобы настроить `CMFCToolBarFontSizeComboBox` объекта. Пример показано, как получить размер шрифта в твипах из текстового поля, заполнить поле со списком размер шрифта все допустимые размеры данного шрифта и укажите размер шрифта в твипах. Этот фрагмент кода входит в состав [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
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
 Эта функция вызывается, если вы хотите синхронизировать данные между выделение в поле со списком и одно поле со списком размер шрифта, такие как [CMFCToolBarFontComboBox класса](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
##  <a name="settwipsize"></a>CMFCToolBarFontSizeComboBox::SetTwipSize  
 Округляет число указанный размер (в твипах) до ближайшего размера в точках и затем задает выбранный размер в поле со списком с этим значением.  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nSize`  
 Указывает размер шрифта (в твипах) для установки.  
  
### <a name="remarks"></a>Примечания  
 Позже предыдущий размер допустимый шрифт можно получить, вызвав [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) метод.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)



