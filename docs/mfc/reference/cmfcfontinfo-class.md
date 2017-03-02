---
title: "Класс CMFCFontInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontInfo class
- CMFCFontInfo::CMFCFontInfo constructor
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
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
ms.openlocfilehash: ac1409bcfce389cbc334edd2b864f7505d7443c7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontinfo-class"></a>Класс CMFCFontInfo
`CMFCFontInfo` Класс описывает имя и другие атрибуты шрифта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCFontInfo`|Создает объект `CMFCFontInfo`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|Получает сцепленные имена шрифта и его значение (сценарий).|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Значение, указывающее набор символов (сценарий), связанные со шрифтом.|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Значение, указывающее шаг и семейство шрифта.|  
|[CMFCFontInfo::m_nType](#m_ntype)|Значение, указывающее тип шрифта.|  
|[CMFCFontInfo::m_strName](#m_strname)|Имя шрифта; например **Arial**.|  
|[CMFCFontInfo::m_strScript](#m_strscript)|Имя набора символов (сценарий), связанные со шрифтом.|  
  
## <a name="remarks"></a>Примечания  
 Можно присоединить `CMFCFontInfo` объект для элемента [CMFCToolBarFontComboBox класса](../../mfc/reference/cmfctoolbarfontcombobox-class.md) класса. Вызов [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) метод, чтобы получить указатель на `CMFCFontInfo` объект.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать различные члены `CMFCFontInfo` класса. В примере показано, как получить `CMFCFontInfo` объекта из `CMFCRibbonFontComboBox`и как получить доступ к ее локальных переменных. Этот пример является частью [2007 демонстрационного MSOffice](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo №&6;](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarfontcombobox.h  
  
##  <a name="a-namecmfcfontinfoa--cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a>CMFCFontInfo::CMFCFontInfo  
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
 Значение, указывающее тип шрифта. Этот параметр может иметь побитовое сочетание (или) DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.  
  
 [in] `src`  
 Существующий `CMFCFontInfo` , члены которого используются для создания данного объекта `CMFCFontInfo` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 В этой документации термины *кодировку* и *сценарий* взаимозаменяемо. Объект *сценарий*, который называется также системе письма, — это совокупность символов и правила для записи этих символов в одном или нескольких языках. Коллекция символов включает алфавит и знаки препинания, используемые в скрипте. Например его говорят в США, а его алфавита включает символы от A до Z латинского алфавита используется для английского языка. `lfCharSet` Членом [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структура определяет набор символов. Например, значение `ANSI_CHARSET` указывает [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] набор символов, который включает в себя алфавита латинского алфавита.  
  
##  <a name="a-namegetfullnamea--cmfcfontinfogetfullname"></a><a name="getfullname"></a>CMFCFontInfo::GetFullName  
 Получает сцепленные имена шрифта и его значение (сценарий).  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая имя шрифта и сценарий.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для получения полного имени шрифта. Например, если имя шрифта будет `Arial` и начертание шрифта `Cyrillic`, этот метод возвращает «Arial (кириллица)».  
  
##  <a name="a-namemncharseta--cmfcfontinfomncharset"></a><a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet  
 Значение, указывающее набор символов (сценарий), связанные со шрифтом.  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `nCharSet` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="a-namemnpitchandfamilya--cmfcfontinfomnpitchandfamily"></a><a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily  
 Значение, указывающее высоту (размер) и семейство шрифта (например, serif, sans-serif и моноширинный).  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `nPitchAndFamily` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="a-namemntypea--cmfcfontinfomntype"></a><a name="m_ntype"></a>CMFCFontInfo::m_nType  
 Значение, указывающее тип шрифта.  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `nType` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="a-namemstrnamea--cmfcfontinfomstrname"></a><a name="m_strname"></a>CMFCFontInfo::m_strName  
 Имя шрифта: например, **Arial**.  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе `lpszName` параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.  
  
##  <a name="a-namemstrscripta--cmfcfontinfomstrscript"></a><a name="m_strscript"></a>CMFCFontInfo::m_strScript  
 Имя набора символов (сценарий), связанные со шрифтом.  
  
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

