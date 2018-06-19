---
title: Класс CMFCRibbonFontComboBox | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86a46614cdb61e39af1016e496b12518b87f59ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370511"
---
# <a name="cmfcribbonfontcombobox-class"></a>Класс CMFCRibbonFontComboBox
Реализует поле со списком, содержащее список шрифтов. Необходимо задать поле со списком на панели ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Деструктор.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Создает и инициализирует объект `CMFCRibbonFontComboBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Заполняет поле со списком шрифтов на ленте на основе таких заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|  
|`CMFCRibbonFontComboBox::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Возвращает указанный набор символов.|  
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||  
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Возвращает типы шрифтов, отображаемые в поле со списком. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Возвращает шаг и семейство шрифтов, отображаемых в поле со списком.|  
|`CMFCRibbonFontComboBox::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Заполняет поле со списком шрифтов на ленте на основе таких ранее заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|  
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Выбирает указанный шрифт в поле со списком.|  
  
## <a name="remarks"></a>Примечания  
 После создания `CMFCRibbonFontComboBox` , добавьте ее на панель ленты, вызвав [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonComboBox.h  
  
##  <a name="buildfonts"></a>  CMFCRibbonFontComboBox::BuildFonts  
 Заполняет поле со списком на ленте со шрифтами.  
  
```  
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nFontType`  
 Указывает тип шрифта шрифтов для добавления.  
  
 [in] `nCharSet`  
 Указывает кодировку шрифтов для добавления.  
  
 [in] `nPitchAndFamily`  
 Задает шаг и семейство шрифтов для добавления.  
  
##  <a name="cmfcribbonfontcombobox"></a>  CMFCRibbonFontComboBox::CMFCRibbonFontComboBox  
 Создает и инициализирует [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) объекта.  
  
```  
CMFCRibbonFontComboBox(
    UINT nID,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH,  
    int nWidth = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор команды команду, которая выполняется, когда пользователь выбирает элемент в поле со списком.  
  
 [in] `nFontType`  
 Указывает типы шрифт для отображения в поле со списком. Допустимые значения: **значения: DEVICE_FONTTYPE**, **RASTER_FONTTYPE**, и **TRUETYPE_FONTTYPE**, или все битовые комбинации.  
  
 [in] `nCharSet`  
 Фильтрует шрифтов в поле со списком теми, которые принадлежат кодировку...  
  
 [in] `nPitchAndFamily`  
 Задает шаг и семейство шрифтов, отображаемых в поле со списком.  
  
 [in] `nWidth`  
 Ширина в пикселях, поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о возможных `nFontType` значения параметров в разделе [EnumFontFamProc](http://msdn.microsoft.com/library/windows/desktop/dd162621) в документации пакета SDK для Windows.  
  
 Дополнительные сведения о допустимых кодировок, которые могут быть назначены `nCharSet`и их допустимых значений, которые могут быть назначены `nPitchAndFamily`, в разделе [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) документации по пакету Windows SDK.  
  
##  <a name="getfontdesc"></a>  CMFCRibbonFontComboBox::GetFontDesc  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="rebuildfonts"></a>  CMFCRibbonFontComboBox::RebuildFonts  
 Заполняет поле со списком на ленте со шрифтами типа ранее указанного шрифта, набор символов и шаг и семейство.  
  
```  
void RebuildFonts();
```  
  
### <a name="remarks"></a>Примечания  
 Можно указать тип шрифта, набор символов и шаг и семейство шрифтов для включения в поле со списком шрифтов ленты в [конструктор](#cmfcribbonfontcombobox) для этого класса или путем вызова [CMFCRibbonFontComboBox::BuildFonts](#buildfonts).  
  
##  <a name="setfont"></a>  CMFCRibbonFontComboBox::SetFont  
 Выбирает указанный шрифт в поле со списком.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BOOL bExact = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Задает имя шрифта для выбора.  
  
 `nCharSet`  
 Указывает кодировку для выбранного шрифта.  
  
 `bExact`  
 `TRUE` Чтобы указать, что набор символов должно соответствовать при выборе шрифта; `FALSE` для указания того, при выборе шрифта может игнорироваться набор символов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если указанный шрифт был найден и установлен; в противном случае возвращается ноль.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcharset"></a>  CMFCRibbonFontComboBox::GetCharSet  
 Возвращает указанный набор символов.  
  
```  
BYTE GetCharSet() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Набор символов (см. LOGFONT документации по пакету Windows SDK).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getfonttype"></a>  CMFCRibbonFontComboBox::GetFontType  
 Возвращает типы шрифтов, отображаемые в поле со списком. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.  
  
```  
int GetFontType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Типы шрифтов (см. EnumFontFamProc в документации Windows SDK).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpitchandfamily"></a>  CMFCRibbonFontComboBox::GetPitchAndFamily  
 Возвращает шаг и семейство шрифтов, отображаемых в поле со списком.  
  
```  
BYTE GetPitchAndFamily() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Шаг и семейство (см. LOGFONT документации по пакету Windows SDK).  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)
