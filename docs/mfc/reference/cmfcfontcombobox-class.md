---
title: "Класс CMFCFontComboBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox::DrawItem method
- CMFCFontComboBox::PreTranslateMessage method
- CMFCFontComboBox::MeasureItem method
- CMFCFontComboBox class
- CMFCFontComboBox::CompareItem method
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
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
ms.openlocfilehash: 1252f5ca102637e70cc384afd723464aec4144b4
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontcombobox-class"></a>Класс CMFCFontComboBox
`CMFCFontComboBox` Класс создает поле со списком, содержащее список шрифтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Создает объект `CMFCFontComboBox`.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|Вызывается средой, чтобы определить относительное положение элемента в поле отсортированный список текущего шрифта со списком. (Переопределяет [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|Вызывается платформой для рисования в текущий элемент управления поля со списком шрифта указанного элемента. (Переопределяет [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|Извлекает сведения о текущего выбранного шрифта.|  
|`CMFCFontComboBox::MeasureItem`|Вызывается платформой для информирования Windows измерений в списке в текущий элемент управления поля со списком шрифта. (Переопределяет [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|Преобразует оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|Выбирает шрифт, который соответствует заданным критериям, в поле со списком Шрифт.|  
|[CMFCFontComboBox::Setup](#setup)|Инициализирует список элементов в поле со списком шрифта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Указывает платформу какой шрифт, используемый для рисования метки элемента в поле со списком текущего шрифта.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CMFCFontComboBox` в диалоговом окне, добавьте `CMFCFontComboBox` переменной в классе диалогового окна. Затем в `OnInitDialog` класс диалогового окна, вызов метода [CMFCFontComboBox::Setup](#setup) метод для инициализации список элементов в поле со списком.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxfontcombobox.h  
  
##  <a name="a-namecmfcfontcomboboxa--cmfcfontcomboboxcmfcfontcombobox"></a><a name="cmfcfontcombobox"></a>CMFCFontComboBox::CMFCFontComboBox  
 Создает объект `CMFCFontComboBox`.  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetselfonta--cmfcfontcomboboxgetselfont"></a><a name="getselfont"></a>CMFCFontComboBox::GetSelFont  
 Извлекает сведения о текущего выбранного шрифта.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CMFCFontInfo класса](../../mfc/reference/cmfcfontinfo-class.md) , описывающий шрифт. Он может быть `NULL` при выборе какой-либо шрифт в поле со списком.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namembdrawusingfonta--cmfcfontcomboboxmbdrawusingfont"></a><a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont  
 Указывает платформу какой шрифт, используемый для рисования метки элемента в поле со списком текущего шрифта.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для направления framework использовать тот же шрифт для рисования каждого элемента label. Значение этого элемента `FALSE` для направления framework для рисования каждой подписи с использованием шрифта, имя которого совпадает с метки. Значение по умолчанию для этого элемента — `FALSE`.  
  
##  <a name="a-nameselectfonta--cmfcfontcomboboxselectfont"></a><a name="selectfont"></a>CMFCFontComboBox::SelectFont  
 Выбирает шрифт, который соответствует заданным критериям, в поле со списком Шрифт.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDesc`  
 Указывает описание объект шрифта.  
  
 [in] `lpszName`  
 Задает имя шрифта.  
  
 [in] `nCharSet`  
 Указывает набор символов. Значение по умолчанию — DEFAULT_CHARSET. Дополнительные сведения см. в разделе `lfCharSet` членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент в поле со списком шрифта соответствующий объект описания указанного шрифта или имя шрифта и charset; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы выбрать и прокрутите до элемента в поле со списком Шрифт, соответствующий заданным шрифтом.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SelectFont` метод `CMFCFontComboBox` класса. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#35;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="a-namesetupa--cmfcfontcomboboxsetup"></a><a name="setup"></a>CMFCFontComboBox::Setup  
 Инициализирует список элементов в поле со списком шрифта.  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nFontType`  
 Указывает тип шрифта. Значение по умолчанию — побитовое сочетание (или) DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.  
  
 [in] `nCharSet`  
 Указывает кодировку шрифта. Значение по умолчанию — DEFAULT_CHARSET.  
  
 [in] `nPitchAndFamily`  
 Задает высоту шрифта и семейства. Значение по умолчанию — DEFAULT_PITCH.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если поле со списком шрифта был инициализирован успешно. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод инициализирует поле со списком Шрифт, перечисление установленных шрифтов, которые совпадают с указанными параметрами и вставки этих имен шрифтов в поле со списком шрифта.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Setup` метод `CMFCFontComboBox` класса. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#36;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)

