---
title: Класс CSmartDockingInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3328eacb9789b892a271208193e82546eb73f7e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373671"
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
|[CSmartDockingInfo::CopyTo](#copyto)|Копирует текущий смарт-закрепления параметры сведения в предоставленный [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Указывает, следует ли использовать текущий цвет темы, когда платформа отображает интеллектуальных маркеров закрепления.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Задает цвет фона базовый интеллектуальных маркеров закрепления.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Задает цвет, который заменяет `m_clrToneSrc` в смарт-закрепления растровые изображения маркера.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Задает цвет смарт-закрепления растровые изображения маркера.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Задает цвет смарт-закрепления точечных рисунков маркера, если они являются прозрачными.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Задает смещение центральной группой интеллектуальных маркеров закрепления из границы прямоугольника, центральная группа.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Указывает общий объем всех интеллектуальных маркеров закрепления в группе.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Определяет идентификаторы точечных рисунков, платформа использует для интеллектуальных маркеров закрепления не выделяемых ресурсов.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Определяет идентификаторы точечных рисунков, платформа использует для интеллектуальных маркеров закрепления, выделенных ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 Framework маркеры смарт-закрепления маркеры внутренним образом. На следующем рисунке показан стандартный интеллектуальных маркеров закрепления:  
  
 ![Стандартные маркеры смарт-закрепления](../../mfc/reference/media/nextsdmarkers.png "nextsdmarkers")  
  
 На этом рисунке на рисунке слева показано центральная группа смарт-закрепления маркер, который не поддерживает закрепление на вкладку включена. Изображение в середине показывает смарт-закрепления маркер правой границы. Изображение справа показывает центральная группа смарт-закрепления маркер, который имеет закрепление на вкладку включена. Центральная группа смарт-закрепления маркера имеет основной растрового изображения и пять смарт-закрепления растровые изображения маркера.  
  
 Можно настроить следующие параметры интеллектуальных маркеров закрепления.  
  
-   Цвет. Например синий цвет маркеров на рисунке можно заменить любой цвет, определяемой пользователем.  
  
-   Цвет прозрачности.  
  
-   Смещение маркера смарт-закрепления в группе центра от границы ограничивающего прямоугольника.  
  
-   Основной точечного рисунка, который представляет группу центра.  
  
-   Точечные рисунки, представляющий обычных и выделенный интеллектуальных маркеров закрепления.  
  
 Ниже показан пример вид интеллектуальных маркеров закрепления, которые были изменены.  
  
 ![Пользовательские маркеры смарт-закрепления](../../mfc/reference/media/nextsdmarkerscustom.png "nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDockingManager.h  
  
##  <a name="copyto"></a>  CSmartDockingInfo::CopyTo  
 Копирует текущие параметры смарт-закрепления в предоставленный [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) объекта.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `params`  
 Объект типа `CSmartDockingInfo` заполняется текущие параметры смарт-закрепления.  
  
##  <a name="m_busethemecolorinshading"></a>  CSmartDockingInfo::m_bUseThemeColorInShading  
 Указывает, следует ли использовать текущий цвет темы, когда платформа отображает интеллектуальных маркеров закрепления.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, маркеры, отображаются с помощью текущего цвета темы; в противном случае отображаются маркеры с светло-синим цветом.  
  
 Значение по умолчанию — `FALSE`.  
  
##  <a name="m_clrbasebackground"></a>  CSmartDockingInfo::m_clrBaseBackground  
 Задает цвет фона базовый интеллектуальных маркеров закрепления.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>  CSmartDockingInfo::m_clrToneDest  
 Задает цвет, который будет заменен `m_clrToneSrc` в смарт-закрепления растровые изображения маркера.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение используется для изменения цвета точечных рисунков маркера программными средствами. Например, если вы хотите изменить цвет стандартные маркеры, предоставленные с помощью платформы, это значение равно нужный цвет. По умолчанию [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) задано значение RGB (61, 123, 241) (сине цвет).  
  
 Чтобы изменить цвет пользовательских маркеров, необходимо указать `m_clrToneDest` и `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>  CSmartDockingInfo::m_clrToneSrc  
 Задает цвет смарт-закрепления растровые изображения маркера.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение только в том случае, если вы хотите заменить другой цвет цвет пользовательского растрового изображения. Необходимо задать значение, если изменяется цвет стандартного (функция) маркера.  
  
 Используйте `(COLORREF)-1` оставить пустым члена группы смарт-закрепления.  
  
##  <a name="m_clrtransparent"></a>  CSmartDockingInfo::m_clrTransparent  
 Задает цвет смарт-закрепления точечных рисунков маркера, если они являются прозрачными.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение задается при отображении пользовательские маркеры и пользовательские растровые изображения в группе закрепления.  
  
##  <a name="m_ncentralgroupoffset"></a>  CSmartDockingInfo::m_nCentralGroupOffset  
 Задает смещение между центральная группа вид интеллектуальных маркеров закрепления и границы прямоугольника, центральная группа.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте это значение, если вы хотите изменить смещение по умолчанию между пользовательские маркеры и границы центральная группа вид интеллектуальных маркеров закрепления. Смещение по умолчанию составляет 5 пикселей.  
  
##  <a name="m_sizetotal"></a>  CSmartDockingInfo::m_sizeTotal  
 Указывает общий объем прямоугольник, ограничивающий все маркеры смарт-закрепления в группе центра.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Примечания  
 Задать `m_sizeTotal` размер маркера центральная группа ограничивающего прямоугольника. Необходимо указать это значение, если вы используете пользовательские растровые изображения маркеров.  
  
##  <a name="m_uimarkerbmpresid"></a>  CSmartDockingInfo::m_uiMarkerBmpResID  
 Определяет ресурс идентификаторы точечных рисунков, которые используются для без подсветки пользовательских интеллектуальных маркеров закрепления.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Примечания  
 Заполнение массива идентификаторы точечных рисунков, представляющий интеллектуальных маркеров закрепления ресурсов. `AFX_SD_MARKERS_NUM` в настоящее время определяется как 5. Заполните массив следующим образом:  
  
 `params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;`  
  
 `params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;`  
  
 `params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;`  
  
 `params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;`  
  
 `params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;`  
  
##  <a name="m_uimarkerlightbmpresid"></a>  CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Определяет идентификаторы точечных рисунков, которые используются для выделенных пользовательские маркеры смарт-закрепления ресурсов.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Примечания  
 Заполните этот массив с идентификаторами точечных рисунков, представляющий выделенный интеллектуальных маркеров закрепления. `AFX_SD_MARKERS_NUM` в настоящее время определяется как 5. Заполните массив следующим образом:  
  
 `params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;`  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)
