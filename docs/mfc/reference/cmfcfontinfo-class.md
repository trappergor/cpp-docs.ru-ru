---
title: Класс CMFCFontInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9e4c1031ba06eaabe67418a018f95d689f71d1e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcfontinfo-class"></a>Класс CMFCFontInfo
`CMFCFontInfo` Класс описывает имя и другие атрибуты шрифта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCFontInfo`|Создает объект `CMFCFontInfo`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|Возвращает сцепленные имена шрифта и ее символ набора (сценарий).|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Значение, указывающее набор символов (сценарий), связанных с шрифтом.|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Значение, указывающее шаг и семейство шрифта.|  
|[CMFCFontInfo::m_nType](#m_ntype)|Значение, указывающее тип шрифта.|  
|[CMFCFontInfo::m_strName](#m_strname)|Имя шрифта; например **Arial**.|  
|[CMFCFontInfo::m_strScript](#m_strscript)|Имя набора символов (сценарий), связанных с шрифтом.|  
  
## <a name="remarks"></a>Примечания  
 Можно присоединить `CMFCFontInfo` объекта для элемента, [CMFCToolBarFontComboBox класса](../../mfc/reference/cmfctoolbarfontcombobox-class.md) класса. Вызовите [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) метод, чтобы получить указатель на `CMFCFontInfo` объект.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные члены `CMFCFontInfo` класса. В примере показано, как получить `CMFCFontInfo` объекта из `CMFCRibbonFontComboBox`и как осуществляется доступ к ее локальных переменных. Данный пример является частью [MSOffice 2007 демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfcfontinfo"></a>  CMFCFontInfo::CMFCFontInfo  
 Создает объект `CMFCFontInfo`.  
  
```  
CMFCFontInfo(
    LPCTSTR lpszName,  
    LPCTSTR lpszScript,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily,  
    int nType);  
  
CMFCFontInfo(const CMFCFontInfo& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя шрифта. Дополнительные сведения см. в разделе `lfFaceName` членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры.  
  
 [in] `lpszScript`  
 Имя шрифта сценарий (набор символов).  
  
 [in] `nCharSet`  
 Значение, указывающее набор символов (сценарий) шрифта. Дополнительные сведения см. в разделе `lfCharSet` членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры.  
  
 [in] `nPitchAndFamily`  
 Значение, указывающее шаг и семейство шрифта. Дополнительные сведения см. в разделе `lfPitchAndFamily` членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры.  
  
 [in] `nType`  
 Значение, указывающее тип шрифта. Этот параметр может иметь побитовое сочетание (OR) значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.  
  
 [in] `src`  
 Существующий `CMFCFontInfo` , члены которого используются для создания объекта `CMFCFontInfo` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 В этой документации используются термины *кодировку* и *сценарий* попеременно. Объект *сценарий*, который называется также системе письма, — это совокупность символы и правила для записи этих символов в один или несколько языков. Коллекция символов включает в себя буквы и знаки препинания, используемые в скрипте. Например как его произносятся в США, и его алфавита включает символы от A до Z латинского алфавита используется для английского языка. `lfCharSet` Членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структура указывает набор символов. Например, значение `ANSI_CHARSET` указывает [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] набора символов, включая буквы латинского алфавита.  
  
##  <a name="getfullname"></a>  CMFCFontInfo::GetFullName  
 Возвращает сцепленные имена шрифта и ее символ набора (сценарий).  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая имя шрифта и сценарий.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для получения полного имени шрифта. Например, если имя шрифта будет `Arial` и начертание шрифта `Cyrillic`, этот метод возвращает «Arial (кириллица)».  
  
##  <a name="m_ncharset"></a>  CMFCFontInfo::m_nCharSet  
 Значение, указывающее набор символов (сценарий), связанных с шрифтом.  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `nCharSet` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="m_npitchandfamily"></a>  CMFCFontInfo::m_nPitchAndFamily  
 Значение, указывающее шаг (размер) и семейство шрифта (например, serif, sans-serif и моноширинного).  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `nPitchAndFamily` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="m_ntype"></a>  CMFCFontInfo::m_nType  
 Значение, указывающее тип шрифта.  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `nType` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="m_strname"></a>  CMFCFontInfo::m_strName  
 Имя шрифта: например, **Arial**.  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `lpszName` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="m_strscript"></a>  CMFCFontInfo::m_strScript  
 Имя набора символов (сценарий), связанных с шрифтом.  
  
```  
const CString m_strScript;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `lpszScript` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [Класс CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
