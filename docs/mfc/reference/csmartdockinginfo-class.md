---
title: "Класс CSmartDockingInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
dev_langs:
- C++
helpviewer_keywords:
- CSmartDockingInfo class
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
caps.latest.revision: 27
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9ae735b202299d26b98ec763f65c3f8772d9b914
ms.lasthandoff: 02/24/2017

---
# <a name="csmartdockinginfo-class"></a>Класс CSmartDockingInfo
Определяет внешний вид интеллектуальных маркеров закрепления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](#copyto)|Копирует текущий смарт-закрепления параметры info в предоставленный [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Указывает, следует ли использовать текущий цвет темы, когда платформа отображает интеллектуальные маркеры стыковки.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Указывает цвет фона базовый интеллектуальные маркеры стыковки.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Задает цвет, который заменяет `m_clrToneSrc` в смарт-закрепления растровые изображения маркера.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Задает цвет смарт-закрепления растровые изображения маркера.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Задает цвет смарт-закрепления точечных рисунков маркер, когда они являются прозрачными.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Задает смещение центральной группы интеллектуальные маркеры стыковки из границ прямоугольника центральная группа.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Задает общий размер всех интеллектуальные маркеры стыковки в группе.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Определяет идентификаторы точечных рисунков, платформа использует для интеллектуальные маркеры стыковки не выделяемых ресурсов.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Определяет идентификаторы точечных рисунков, платформа использует для интеллектуальные маркеры стыковки, выделенных ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 Дескрипторы framework внутренне смарт-маркеров закрепления. Стандартные интеллектуальные маркеры стыковки на следующем рисунке:  
  
 ![Стандартные маркеры смарт-закрепления](../../mfc/reference/media/nextsdmarkers.png "nextsdmarkers")  
  
 На этом рисунке на рисунке слева показано центральная группа смарт-закрепления маркер, который не поддерживает закрепление на вкладку включен. В середине рисунке смарт-закрепления маркер правой границы. На изображении справа показано центральная группа смарт-закрепления маркер, у которой есть на вкладку включено закрепление. Центральная группа смарт-закрепления маркер имеет основной точечного рисунка и пять смарт-закрепления растровые изображения маркера.  
  
 Можно настроить следующие параметры интеллектуальные маркеры стыковки:  
  
-   Цвет. Например синий цвет маркеров на рисунке можно заменить любой определенный пользователем цвет.  
  
-   Цвет прозрачности.  
  
-   Смещение смарт-закрепления маркера центральной группы от границы ограничивающего прямоугольника.  
  
-   Основной растровое изображение, представляющее центральная группа.  
  
-   Точечные рисунки, представляющий интеллектуальные маркеры стыковки обычных и выделенным.  
  
 Ниже показан пример интеллектуальные маркеры стыковки, настроенных:  
  
 ![Пользовательские маркеры смарт-закрепления](../../mfc/reference/media/nextsdmarkerscustom.png "nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDockingManager.h  
  
##  <a name="copyto"></a>CSmartDockingInfo::CopyTo  
 Копирует текущие параметры смарт-закрепления в указанных [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) объекта.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `params`  
 Объект типа `CSmartDockingInfo` заполняется текущие параметры смарт-закрепления.  
  
##  <a name="m_busethemecolorinshading"></a>CSmartDockingInfo::m_bUseThemeColorInShading  
 Указывает, следует ли использовать текущий цвет темы, когда платформа отображает интеллектуальные маркеры стыковки.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, маркеры, отображаются с помощью текущего цвета темы; в противном случае отображаются маркеры с голубым цветом.  
  
 Значение по умолчанию — `FALSE`.  
  
##  <a name="m_clrbasebackground"></a>CSmartDockingInfo::m_clrBaseBackground  
 Указывает цвет фона базовый интеллектуальные маркеры стыковки.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>CSmartDockingInfo::m_clrToneDest  
 Задает цвет, который заменит `m_clrToneSrc` в смарт-закрепления растровые изображения маркера.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение программно изменить цвет маркера точечных рисунков. Например, если вы хотите изменить цвет стандартные маркеры, предоставляемые с помощью платформы, это значение равно нужный цвет. По умолчанию [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) задано значение RGB (61, 123, 241) (сине цвет).  
  
 Чтобы изменить цвет пользовательские маркеры, необходимо указать `m_clrToneDest` и `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>CSmartDockingInfo::m_clrToneSrc  
 Задает цвет смарт-закрепления растровые изображения маркера.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение только в том случае, если вы хотите заменить цвет пользовательского точечного рисунка с другой цвет. Необходимо задать это значение, если изменяется цвет standard (предоставляемых framework) маркера.  
  
 Используйте `(COLORREF)-1` для члена группы смарт-закрепления оставьте пустым.  
  
##  <a name="m_clrtransparent"></a>CSmartDockingInfo::m_clrTransparent  
 Задает цвет смарт-закрепления точечных рисунков маркер, когда они являются прозрачными.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение задается при отображении пользовательские маркеры и пользовательских точечных рисунков в группе закрепления.  
  
##  <a name="m_ncentralgroupoffset"></a>CSmartDockingInfo::m_nCentralGroupOffset  
 Указывает смещение между центральной группы интеллектуальные маркеры стыковки и границы прямоугольника центральная группа.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте это значение, если вы хотите изменить смещение по умолчанию между пользовательские маркеры и границы центральной группы интеллектуальные маркеры стыковки. Смещение по умолчанию — 5 пикселей.  
  
##  <a name="m_sizetotal"></a>CSmartDockingInfo::m_sizeTotal  
 Задает общий размер ограничивающего прямоугольника, включающего все маркеры смарт-закрепления в группе центра.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте `m_sizeTotal` размер ограничивающего прямоугольника маркера центральной группы. Необходимо указать это значение при использовании пользовательских точечных рисунков для маркеров.  
  
##  <a name="m_uimarkerbmpresid"></a>CSmartDockingInfo::m_uiMarkerBmpResID  
 Определяет идентификаторы точечных рисунков, которые используются для без подсветки пользовательских интеллектуальные маркеры стыковки ресурсов.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Примечания  
 Этот массив заполняется идентификаторы точечных рисунков, представляющий интеллектуальные маркеры стыковки ресурсов. `AFX_SD_MARKERS_NUM`в настоящее время определяется как 5. Заполнение массива следующим образом:  
  
 `params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;`  
  
 `params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;`  
  
 `params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;`  
  
 `params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;`  
  
 `params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;`  
  
##  <a name="m_uimarkerlightbmpresid"></a>CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Определяет идентификаторы точечных рисунков, которые используются для выделенного пользовательские маркеры смарт-закрепления ресурсов.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Примечания  
 Этот массив заполняется идентификаторы точечных рисунков, представляющий выделенный интеллектуальные маркеры стыковки ресурсов. `AFX_SD_MARKERS_NUM`в настоящее время определяется как 5. Заполнение массива следующим образом:  
  
 `params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;`  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)

