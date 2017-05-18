---
title: "Класс CFontHolder | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
dev_langs:
- C++
helpviewer_keywords:
- custom fonts
- CFontHolder class
- fonts, ActiveX controls
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fdfa16756ff218159087969f2a4967ed5e76a445
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cfontholder-class"></a>Класс CFontHolder
Реализует свойство Font и инкапсулирует функциональность объекта шрифта Windows и интерфейса `IFont` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|Создает объект `CFontHolder`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](#getdisplaystring)|Возвращает строку, отображаемую в браузере свойств контейнера.|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Возвращает шрифт `IDispatch` интерфейса.|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Возвращает дескриптор шрифта Windows.|  
|[CFontHolder::InitializeFont](#initializefont)|Инициализирует `CFontHolder` объекта.|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Возвращает сведения о связанных шрифтов.|  
|[CFontHolder::ReleaseFont](#releasefont)|Отключает `CFontHolder` объекта из `IFont` и `IFontNotification` интерфейсов.|  
|[CFontHolder::Select](#select)|Выбирает шрифт ресурса в контексте устройства.|  
|[CFontHolder::SetFont](#setfont)|Подключается `CFontHolder` объект `IFont` интерфейса.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|Указатель на `CFontHolder` объекта `IFont` интерфейса.|  
  
## <a name="remarks"></a>Примечания  
 `CFontHolder`не имеет базового класса.  
  
 Этот класс используется для реализации свойств пользовательского шрифта для элемента управления. Дополнительные сведения о создании таких свойств, см. в статье [элементы управления ActiveX: шрифты с помощью](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CFontHolder`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="cfontholder"></a>CFontHolder::CFontHolder  
 Создает объект `CFontHolder`.  
  
```  
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```  
  
### <a name="parameters"></a>Параметры  
 *pNotify*  
 Указатель на шрифт `IPropertyNotifySink` интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать метод `InitializeFont` для инициализации результирующего объекта перед его использованием.  
  
##  <a name="getdisplaystring"></a>CFontHolder::GetDisplayString  
 Извлекает строку, которая может отображаться в обозревателе свойств контейнера.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Параметры  
 `strValue`  
 Ссылка на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , предназначенный для отображения строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка успешно извлечено; в противном случае — 0.  
  
##  <a name="getfontdispatch"></a>CFontHolder::GetFontDispatch  
 Вызовите эту функцию, чтобы получить указатель на интерфейс диспетчеризации шрифта.  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CFontHolder` объекта **IFontDisp** интерфейса. Обратите внимание, что функция, вызывает `GetFontDispatch` необходимо вызвать `IUnknown::Release` на этот указатель интерфейса, когда требуется.  
  
### <a name="remarks"></a>Примечания  
 Вызов `InitializeFont` перед вызовом метода `GetFontDispatch`.  
  
##  <a name="getfonthandle"></a>CFontHolder::GetFontHandle  
 Эта функция вызывается для получения дескриптора шрифт Windows.  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Параметры  
 `cyLogical`  
 Высота в логических единицах прямоугольника, в котором рисуется элемент управления.  
  
 `cyHimetric`  
 Высота в `MM_HIMETRIC` единиц элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор объекта шрифта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Отношение `cyLogical` и `cyHimetric` используются для вычисления размера корректного отображения, в логических единицах выражается размер шрифта в `MM_HIMETRIC` единицы:  
  
 Отображение размера = ( `cyLogical`  /  `cyHimetric`) X размер шрифта  
  
 Версия без параметров возвращает дескриптор шрифта правильные размеры для экрана.  
  
##  <a name="initializefont"></a>CFontHolder::InitializeFont  
 Инициализирует `CFontHolder` объекта.  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pFontDesc`  
 Указатель на структуру описание шрифта ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)), указывающий характеристики шрифта.  
  
 `pFontDispAmbient`  
 Указатель на внешнее свойство шрифт контейнера.  
  
### <a name="remarks"></a>Примечания  
 Если `pFontDispAmbient` не **NULL**, `CFontHolder` клон подключен объект `IFont` интерфейс используется внешнее свойство шрифт контейнера.  
  
 Если `pFontDispAmbient` — **NULL**, создается новый объект Font, либо из описания шрифт, на который указывает `pFontDesc` или если `pFontDesc` — **NULL**, из описания по умолчанию.  
  
 Эта функция вызывается после создания `CFontHolder` объекта.  
  
##  <a name="m_pfont"></a>CFontHolder::m_pFont  
 Указатель на `CFontHolder` объекта `IFont` интерфейса.  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>CFontHolder::QueryTextMetrics  
 Извлекает сведения о физических шрифтов, представленного `CFontHolder` объекта.  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Параметры  
 `lptm`  
 Указатель на [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) структуру, которая будет получать данные.  
  
##  <a name="releasefont"></a>CFontHolder::ReleaseFont  
 Эта функция отключает `CFontHolder` объект из его `IFont` интерфейса.  
  
```  
void ReleaseFont();
```  
  
##  <a name="select"></a>CFontHolder::Select  
 Эта функция используется для выбора шрифта элемента управления в заданном контексте устройства.  
  
```  
CFont* Select(
    CDC* pDC,  
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Контекст устройства, в котором выбран шрифт.  
  
 `cyLogical`  
 Высота в логических единицах прямоугольника, в котором рисуется элемент управления.  
  
 `cyHimetric`  
 Высота в `MM_HIMETRIC` единиц элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на шрифт, который заменяется.  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetFontHandle](#getfonthandle) описание `cyLogical` и `cyHimetric` параметров.  
  
##  <a name="setfont"></a>CFontHolder::SetFont  
 Освобождает все существующие шрифта и подключается `CFontHolder` объект `IFont` интерфейса.  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>Параметры  
 *pNewFont*  
 Указатель на новый `IFont` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CPropExchange](../../mfc/reference/cpropexchange-class.md)

