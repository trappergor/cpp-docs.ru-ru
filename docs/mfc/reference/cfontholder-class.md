---
title: "Класс CFontHolder | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd5f13f2ec48f38fde140361d31a5e08ae6228b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cfontholder-class"></a>Класс CFontHolder
Реализует свойство Font и инкапсулирует функциональность объекта шрифта Windows и интерфейса `IFont` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|Создает объект `CFontHolder`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|Указатель на `CFontHolder` объекта `IFont` интерфейса.|  
  
## <a name="remarks"></a>Примечания  
 `CFontHolder`не имеет базового класса.  
  
 Этот класс можно используйте для реализации свойств пользовательского шрифта для элемента управления. Дополнительные сведения о создании таких свойств, см. в статье [элементы управления ActiveX: использование шрифтов](../../mfc/mfc-activex-controls-using-fonts.md).  
  
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
 Ссылка на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , предназначенный для хранения отображаемой строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка успешно извлечено; в противном случае — 0.  
  
##  <a name="getfontdispatch"></a>CFontHolder::GetFontDispatch  
 Вызывайте эту функцию, чтобы получить указатель на интерфейс диспетчеризации шрифта.  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CFontHolder` объекта **IFontDisp** интерфейса. Обратите внимание, что на функцию, который вызывает `GetFontDispatch` необходимо вызвать `IUnknown::Release` на этот указатель интерфейса, когда требуется.  
  
### <a name="remarks"></a>Примечания  
 Вызовите `InitializeFont` перед вызовом `GetFontDispatch`.  
  
##  <a name="getfonthandle"></a>CFontHolder::GetFontHandle  
 Эта функция вызывается для получения дескриптора для шрифта Windows.  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Параметры  
 `cyLogical`  
 Высота в логических единицах прямоугольника, в котором нарисован элемент управления.  
  
 `cyHimetric`  
 Высота в `MM_HIMETRIC` единицы элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор объекта шрифта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Отношение `cyLogical` и `cyHimetric` используются для вычисления размера правильное отображение, в логических единицах выражается размер шрифта в `MM_HIMETRIC` единиц:  
  
 Размер изображения = ( `cyLogical`  /  `cyHimetric`) X размер шрифта  
  
 Версия без параметров возвращает дескриптор шрифта, размера правильно для экрана.  
  
##  <a name="initializefont"></a>CFontHolder::InitializeFont  
 Инициализирует `CFontHolder` объекта.  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pFontDesc`  
 Указатель на структуру описания шрифтов ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)), указывающий характеристики шрифта.  
  
 `pFontDispAmbient`  
 Указатель на внешнее свойство шрифт контейнера.  
  
### <a name="remarks"></a>Примечания  
 Если `pFontDispAmbient` не **NULL**, `CFontHolder` клон подключен объект `IFont` интерфейс используется внешнее свойство шрифт контейнера.  
  
 Если `pFontDispAmbient` — **NULL**, либо из описания шрифтов, на который указывает создается новый объект Font `pFontDesc` или, если `pFontDesc` — **NULL**, с помощью описания по умолчанию.  
  
 Эта функция вызывается после построения `CFontHolder` объекта.  
  
##  <a name="m_pfont"></a>CFontHolder::m_pFont  
 Указатель на `CFontHolder` объекта `IFont` интерфейса.  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>CFontHolder::QueryTextMetrics  
 Извлекает сведения о физических шрифта, представленного `CFontHolder` объекта.  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Параметры  
 `lptm`  
 Указатель на [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) структуру, которая будет получать данные.  
  
##  <a name="releasefont"></a>CFontHolder::ReleaseFont  
 Эта функция отключается `CFontHolder` объект из его `IFont` интерфейса.  
  
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
 Контекст устройства, в которую установлен шрифт.  
  
 `cyLogical`  
 Высота в логических единицах прямоугольника, в котором нарисован элемент управления.  
  
 `cyHimetric`  
 Высота в `MM_HIMETRIC` единицы элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель шрифта, который требуется заменить.  
  
### <a name="remarks"></a>Примечания  
 В разделе [GetFontHandle](#getfonthandle) обсуждение `cyLogical` и `cyHimetric` параметров.  
  
##  <a name="setfont"></a>CFontHolder::SetFont  
 Освобождает любой существующий шрифт и подключается `CFontHolder` объект `IFont` интерфейса.  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>Параметры  
 *pNewFont*  
 Указатель на новый `IFont` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CPropExchange](../../mfc/reference/cpropexchange-class.md)
