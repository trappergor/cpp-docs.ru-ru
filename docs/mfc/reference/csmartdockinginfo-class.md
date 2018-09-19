---
title: Класс CSmartDockingInfo | Документация Майкрософт
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
ms.openlocfilehash: 653be2fb1847403436bccb86807da382ef09cc25
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018214"
---
# <a name="csmartdockinginfo-class"></a>Класс CSmartDockingInfo
Определяет внешний вид интеллектуальных маркеров закрепления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](#copyto)|Копирует текущие смарт-закрепления параметры info в предоставленный [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Указывает, следует ли использовать текущий цвет темы, когда платформа отображает интеллектуальных маркеров закрепления.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Задает цвет фона базовый вид интеллектуальных маркеров закрепления.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Задает цвет, заменяющий `m_clrToneSrc` в смарт-закрепления растровые изображения маркера.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Указывает цвет смарт-закрепления растровые изображения маркера.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Задает цвет смарт-закрепления точечных рисунков маркера, когда они являются прозрачными.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Задает смещение центральной группы интеллектуальные маркеры стыковки с границы прямоугольника центральная группа.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Указывает общий размер всех интеллектуальных маркеров закрепления в группе.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Определяет идентификаторы точечных рисунков, инфраструктура использует для интеллектуальные маркеры стыковки не выделяемых ресурсов.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Определяет идентификаторы точечных рисунков, инфраструктура использует для интеллектуальных маркеров закрепления, выделенных ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 Framework маркеры смарт-закрепления маркеры внутренним образом. На следующем рисунке показан стандартные интеллектуальные маркеры стыковки:  
  
 ![Стандартные маркеры смарт-закрепления](../../mfc/reference/media/nextsdmarkers.png "nextsdmarkers")  
  
 На этом рисунке на рисунке слева показано центральная группа смарт-закрепления маркер, который не поддерживает закрепление на вкладку включена. На рисунке в середине показан маркер смарт-закрепления правого края. Изображение справа показан центральная группа смарт-закрепления маркер, услугам закрепляемые вкладку "включено". Центральная группа смарт-закрепления маркер имеет Битовая карта основной и пять смарт-закрепления растровые изображения маркера.  
  
 Можно настроить следующие параметры вид интеллектуальных маркеров закрепления.  
  
-   Цвет. Например можно заменить синий цвет маркеров на рисунке с любого цвета, определяемые пользователем.  
  
-   Цвет прозрачности.  
  
-   Смещение маркер смарт-закрепления центральной группы в границе ограничивающего прямоугольника.  
  
-   Основной точечного рисунка, который представляет этой центральной группы.  
  
-   Точечные рисунки, представляющий интеллектуальные маркеры стыковки обычных и выделенный.  
  
 Ниже показан пример вид интеллектуальных маркеров закрепления, настроенные:  
  
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
*params*<br/>
[out] Объект типа `CSmartDockingInfo` , заполняется с использованием текущих параметров смарт-закрепления.  
  
##  <a name="m_busethemecolorinshading"></a>  CSmartDockingInfo::m_bUseThemeColorInShading  
 Указывает, следует ли использовать текущий цвет темы, когда платформа отображает интеллектуальных маркеров закрепления.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если маркеры отрисовываются с использованием текущего цвета темы; в противном случае маркеров рисуются с голубой.  
  
 Значение по умолчанию — FALSE.  
  
##  <a name="m_clrbasebackground"></a>  CSmartDockingInfo::m_clrBaseBackground  
 Задает цвет фона базовый вид интеллектуальных маркеров закрепления.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>  CSmartDockingInfo::m_clrToneDest  
 Задает цвет, который заменит `m_clrToneSrc` в смарт-закрепления растровые изображения маркера.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение используется для изменения цвета точечных рисунков маркера программным способом. Например если вы хотите изменить цвет стандартные маркеры, предоставляемые с помощью платформы, это значение на нужный цвет. По умолчанию [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) имеет значение RGB (61, 123, 241) (сине цвет).  
  
 Чтобы изменить цвет пользовательские маркеры, необходимо указать `m_clrToneDest` и `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>  CSmartDockingInfo::m_clrToneSrc  
 Указывает цвет смарт-закрепления растровые изображения маркера.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение только в том случае, если вы хотите заменить цвет пользовательского точечного рисунка с другой цвет. Необходимо задать это значение, если вы изменяете цвет стандартный (платформу предоставленную) маркера.  
  
 Используйте `(COLORREF)-1` оставить пустым члена группы смарт-закрепления.  
  
##  <a name="m_clrtransparent"></a>  CSmartDockingInfo::m_clrTransparent  
 Задает цвет смарт-закрепления точечных рисунков маркера, когда они являются прозрачными.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение необходимо задать при отображении пользовательские маркеры и пользовательских точечных рисунков в группе закрепления.  
  
##  <a name="m_ncentralgroupoffset"></a>  CSmartDockingInfo::m_nCentralGroupOffset  
 Задает смещение между этой центральной группы интеллектуальные маркеры стыковки и границами прямоугольника центральная группа.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте это значение, если вы хотите изменить смещение по умолчанию между пользовательские маркеры и границы этой центральной группы интеллектуальных маркеров закрепления. Смещение по умолчанию равно 5 пикселям.  
  
##  <a name="m_sizetotal"></a>  CSmartDockingInfo::m_sizeTotal  
 Указывает общий объем прямоугольник, ограничивающий все маркеры смарт-закрепления в группе центра.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте `m_sizeTotal` размер ограничивающего прямоугольника центральная группа маркера. Необходимо указать это значение при использовании пользовательских точечных рисунков для маркеров.  
  
##  <a name="m_uimarkerbmpresid"></a>  CSmartDockingInfo::m_uiMarkerBmpResID  
 Определяет идентификаторы точечных рисунков, которые используются для без подсветки пользовательских интеллектуальные маркеры стыковки ресурсов.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Примечания  
 Заполните этот массив идентификаторов точечных рисунков, представляющий интеллектуальные маркеры стыковки ресурсов. В настоящее время AFX_SD_MARKERS_NUM определяется как 5. Заполнение массива следующим образом:  
  
```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```
  
##  <a name="m_uimarkerlightbmpresid"></a>  CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Определяет идентификаторы точечных рисунков, которые используются для выделенной пользовательские маркеры смарт-закрепления ресурсов.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Примечания  
 Заполните этот массив идентификаторов точечных рисунков, представляющий выделенный интеллектуальные маркеры стыковки ресурсов. В настоящее время AFX_SD_MARKERS_NUM определяется как 5. Заполнение массива следующим образом:  
  
```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)
