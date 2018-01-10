---
title: "Класс CMFCToolBarFontComboBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: "29"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f499c5593460b10957c7d09e01c0f458529df0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbarfontcombobox-class"></a>Класс CMFCToolBarFontComboBox
Кнопка панели инструментов, который содержит поле со списком, позволяющий пользователю выбрать шрифт из списка системных шрифтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Создает объект `CMFCToolBarFontComboBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Возвращает указатель на `CMFCFontInfo` объект для указанного индекса в поле со списком.|  
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Выбирает шрифт в поле со списком шрифтов согласно либо имя шрифта или префикс и набор символов шрифта.|  
  
### <a name="data-members"></a>Элементы данных  
 [CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)  
 Высота символов в поле со списком шрифтов.  
  
## <a name="remarks"></a>Примечания  
 Чтобы добавить кнопки поля со списком шрифтов на панель инструментов, выполните следующие действия.  
  
1.  Зарезервировать идентификатора фиктивный ресурса для кнопки в родительский ресурс панели инструментов.  
  
2.  Создать `CMFCToolBarFontComboBox` объекта.  
  
3.  В обработчике сообщений, который обрабатывает `AFX_WM_RESETTOOLBAR` сообщение, заменить исходного кнопки «Создать» поле со списком с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
4.  Синхронизировать шрифта, выбранного в поле со списком с помощью шрифта в документ с помощью [CMFCToolBarFontComboBox::SetFont](#setfont) метод.  
  
 Чтобы синхронизировать шрифта документа с шрифта, выбранного в поле со списком, используйте [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) метод для извлечения атрибутов выбранного шрифта и эти атрибуты можно использовать для создания [ CFont-класс](../../mfc/reference/cfont-class.md) объекта.  
  
 Вызывает функцию Win32, кнопки поля со списком шрифтов [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) для определения экрана и принтера шрифты, доступные в системе.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontcombobox"></a>CMFCToolBarFontComboBox::CMFCToolBarFontComboBox  
 Создает [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) объекта.  
  
```  
public:  
CMFCToolBarFontComboBox(
    UINT uiID,  
    int iImage,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    DWORD dwStyle = CBS_DROPDOWN,  
    int iWidth = 0,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);

 
protected:  
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,  
    int nFontType,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily);  
  
CMFCToolBarFontComboBox();
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор команды в поле со списком.  
  
 [in] `iImage`  
 Отсчитываемый от нуля индекс изображение кнопки панели инструментов. Образ, находится в [класса CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) объекта, [CMFCToolBar класс](../../mfc/reference/cmfctoolbar-class.md) поддерживает класс.  
  
 [in] `nFontType`  
 Типы шрифтов, которые содержатся в поле со списком. Этот параметр может быть сочетанием следующих значений (логическое или):  
  
 ЗНАЧЕНИЯ: DEVICE_FONTTYPE  
  
 RASTER_FONTTYPE  
  
 TRUETYPE_FONTTYPE  
  
 [in] `nCharSet`  
 Если задано значение DEFAULT_CHARSET, поле со списком содержит все уникальность имен шрифтов в всех наборов символов. (При наличии двух шрифтов с тем же именем, поле со списком содержит один из них.) Если набор набор Допустимое символьное значение, поле со списком содержит только шрифты в указанный набор символов. В разделе [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) список возможных символов задает.  
  
 [in] `dwStyle`  
 Стиль поле со списком. (см. [стили полей со списками](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))  
  
 [in] `iWidth`  
 Ширина в пикселях элемента управления.  
  
 [in] `nPitchAndFamily`  
 Если задано значение DEFAULT_PITCH, поле со списком содержит шрифты независимо от размера. Если значение FIXED_PITCH или VARIABLE_PITCH, поле со списком содержит только шрифты с этим типом шаг. Фильтрация на основе семейства шрифтов в настоящее время не поддерживается.  
  
 [выходной] `pLstFontsExternal`  
 Указатель на [класс CObList](../../mfc/reference/coblist-class.md) объект, который хранит доступных шрифтов.  
  
### <a name="remarks"></a>Примечания  
 Как правило `CMFCToolBarFontComboBox` объектов сохранить список доступных шрифтов в один общий `CObList` объекта. Если использовать вторую перегрузку конструктора и укажите допустимый указатель на `pLstFontsExternal`, `CMFCToolBarFontComboBox` объекта вместо заполнит `CObList` , `pLstFontsExternal` указывает с доступных шрифтов.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCToolBarFontComboBox` объекта. Этот фрагмент кода входит в состав [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]  
  
##  <a name="getfontdesc"></a>CMFCToolBarFontComboBox::GetFontDesc  
 Возвращает указатель на `CMFCFontInfo` объект для указанного индекса в поле со списком.  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Задает отсчитываемый от нуля индекс элемент поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `CMFCFontInfo`. Если `iIndex` указывается индекс допустимый элемент, возвращается значение `NULL`.  
  
##  <a name="m_nfontheight"></a>CMFCToolBarFontComboBox::m_nFontHeight  
 Высота в пикселях символов в поле со списком шрифтов, если поле со списком имеет стиль рисования владельцем.  
  
```  
static int m_nFontHeight  
```  
  
### <a name="remarks"></a>Примечания  
 Если `m_nFontHeight` переменной равно 0, высота вычисляется автоматически в соответствии с шрифт по умолчанию в поле со списком. Высота относится и восхождение символов выше базовых показателей и спуск символов под базовой линии.  
  
##  <a name="setfont"></a>CMFCToolBarFontComboBox::SetFont  
 Выбирает шрифт в поле со списком шрифтов согласно имя шрифта и символ набор, указываются в параметрах.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BOOL bExact=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Задает имя шрифта или префикс.  
  
 [in] `nCharSet`  
 Указывает кодировку.  
  
 [in] `bExact`  
 Указывает, является ли `lpszName` содержит имя шрифта или префикс шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если шрифт установлен успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bExact` — `TRUE`, этот метод выбирает шрифт, который точно соответствует имени, указанного в качестве `lpszName`. Если `bExact` — `FALSE`, этот метод выбирает шрифт, который начинается с текста, указанного как `lpszName` и использует набор символов, которые указаны в качестве `nCharSet`. Если `nCharSet` задано для DEFAULT_CHARSET, набор символов будет игнорируется и только `lpszName` будет использоваться для выбора шрифта.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)



