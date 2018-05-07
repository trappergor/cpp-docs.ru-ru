---
title: Класс CMFCFontComboBox | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b37901bddec6a886ddb1ae538f3294bd9d28d9a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|`CMFCFontComboBox::CompareItem`|Вызывается платформой для определения относительной позиции нового элемента в поле отсортированный список текущего шрифта поле со списком. (Переопределяет [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|Вызывается платформой для отрисовки указанный элемент в текущий шрифт поле со списком. (Переопределяет [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|Извлекает сведения о текущего выбранного шрифта.|  
|`CMFCFontComboBox::MeasureItem`|Вызывается платформой для информирования Windows измерений в списке в текущий шрифт поле со списком. (Переопределяет [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|Преобразует сообщения окна перед их передачей [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|Выбирает шрифт, который удовлетворяет указанным критериям, в поле со списком Шрифт.|  
|[CMFCFontComboBox::Setup](#setup)|Инициализирует список элементов в поле со списком шрифтов.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Указывает шрифт, используемый для отрисовки метки элемента в поле со списком текущий шрифт для платформы.|  
  
## <a name="remarks"></a>Примечания  
 Для использования `CMFCFontComboBox` в диалоговом окне, добавьте `CMFCFontComboBox` переменной класса диалогового окна. Затем в `OnInitDialog` класс диалогового окна, вызов метода [CMFCFontComboBox::Setup](#setup) метод для инициализации список элементов в поле со списком.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox  
 Создает объект `CMFCFontComboBox`.  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont  
 Извлекает сведения о текущего выбранного шрифта.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CMFCFontInfo класса](../../mfc/reference/cmfcfontinfo-class.md) , описывающий шрифта. Это может быть `NULL` при выборе какой-либо шрифт в поле со списком.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont  
 Указывает шрифт, используемый для отрисовки метки элемента в поле со списком текущий шрифт для платформы.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого элемента `TRUE` для направления платформе используется шрифт для отрисовки каждой подписи. Значение этого элемента `FALSE` для направления структурой для прорисовки каждой подписи с помощью шрифта, имя которого совпадает с метки. Значение по умолчанию для этого элемента — `FALSE`.  
  
##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont  
 Выбирает шрифт, который удовлетворяет указанным критериям, в поле со списком Шрифт.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDesc`  
 Указывает на несуществующий объект описания шрифтов.  
  
 [in] `lpszName`  
 Задает имя шрифта.  
  
 [in] `nCharSet`  
 Указывает набор символов. Значение по умолчанию — DEFAULT_CHARSET. Дополнительные сведения см. в разделе `lfCharSet` членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если элемент в поле со списком шрифтов соответствующего объекта описания указанного шрифта или имя шрифта и charset; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для выбора и прокрутки элемента в поле со списком шрифтов, соответствующий заданным шрифтом.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SelectFont` метод `CMFCFontComboBox` класса. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>  CMFCFontComboBox::Setup  
 Инициализирует список элементов в поле со списком шрифтов.  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nFontType`  
 Указывает тип шрифта. Значение по умолчанию — битовую комбинацию (OR) значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.  
  
 [in] `nCharSet`  
 Указывает кодировку шрифта. Значение по умолчанию — DEFAULT_CHARSET.  
  
 [in] `nPitchAndFamily`  
 Указывает шрифт шаг и семейство. Значение по умолчанию — DEFAULT_PITCH.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если поле со списком шрифтов был инициализирован успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод инициализирует поле со списком шрифтов, перечисление установленных шрифтов, которые совпадают с указанными параметрами и вставляя их имена шрифтов в поле со списком шрифтов.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Setup` метод `CMFCFontComboBox` класса. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)
