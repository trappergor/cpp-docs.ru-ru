---
title: Класс CFontHolder | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 344e2e39e52aa80624e4959daada5038506bb4c5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433182"
---
# <a name="cfontholder-class"></a>Класс CFontHolder

Реализует свойство Font и инкапсулирует функциональность объекта шрифта Windows и интерфейса `IFont` .

## <a name="syntax"></a>Синтаксис

```
class CFontHolder
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|Создает объект `CFontHolder`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|Извлекает строку, отображаемую в браузере свойств контейнера.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Возвращает шрифт `IDispatch` интерфейс.|
|[CFontHolder::GetFontHandle](#getfonthandle)|Возвращает дескриптор шрифта Windows.|
|[CFontHolder::InitializeFont](#initializefont)|Инициализирует `CFontHolder` объекта.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Возвращает сведения о связанных шрифтов.|
|[CFontHolder::ReleaseFont](#releasefont)|Отключает `CFontHolder` объекта из `IFont` и `IFontNotification` интерфейсов.|
|[CFontHolder::Select](#select)|Выбирает ресурса шрифта в контексте устройства.|
|[CFontHolder::SetFont](#setfont)|Подключается `CFontHolder` объект `IFont` интерфейс.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|Указатель на `CFontHolder` объекта `IFont` интерфейс.|

## <a name="remarks"></a>Примечания

`CFontHolder` не имеет базового класса.

Этот класс используется для реализации свойств пользовательского шрифта для элемента управления. Сведения о создании таких свойств, см. в статье [элементы управления ActiveX: использование шрифтов](../../mfc/mfc-activex-controls-using-fonts.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CFontHolder`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

##  <a name="cfontholder"></a>  CFontHolder::CFontHolder

Создает объект `CFontHolder`.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>Параметры

*pNotify*<br/>
Указатель на шрифт `IPropertyNotifySink` интерфейс.

### <a name="remarks"></a>Примечания

Необходимо вызвать метод `InitializeFont` для инициализации результирующего объекта перед его использованием.

##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString

Извлекает строку, которая может отображаться в обозревателе свойств контейнера.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Параметры

*strValue*<br/>
Ссылка на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , предназначенный для отображения строки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если строка успешно извлечено; в противном случае 0.

##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch

Вызывайте эту функцию, чтобы получить указатель на интерфейс диспетчеризации шрифта.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CFontHolder` объекта `IFontDisp` интерфейс. Обратите внимание, что на функцию, который вызывает `GetFontDispatch` необходимо вызвать `IUnknown::Release` на этот указатель интерфейса, когда закончила с ним.

### <a name="remarks"></a>Примечания

Вызовите `InitializeFont` перед вызовом `GetFontDispatch`.

##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle

Вызывайте эту функцию для получения дескриптора для шрифта Windows.

```
HFONT GetFontHandle();


HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Параметры

*cyLogical*<br/>
Высота в логических единицах прямоугольника, в которой рисуется элемент управления.

*cyHimetric*<br/>
Высота в единицах MM_HIMETRIC, элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор объекта шрифта; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Доля *cyLogical* и *cyHimetric* используется для вычисления размер правильное отображение в логические блоки, выраженный в единицах измерения MM_HIMETRIC кегль шрифта:

Отображаемый размер = ( *cyLogical* / *cyHimetric*) X размер шрифта

Версия без параметров возвращает дескриптор шрифта, размер экрана правильно.

##  <a name="initializefont"></a>  CFontHolder::InitializeFont

Инициализирует `CFontHolder` объекта.

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Параметры

*pFontDesc*<br/>
Указатель на структуру описание шрифта ( [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc)), указывающий характеристики шрифта.

*pFontDispAmbient*<br/>
Указатель на внешнее свойство шрифт контейнера.

### <a name="remarks"></a>Примечания

Если *pFontDispAmbient* не равно NULL, `CFontHolder` клон подключен объект `IFont` интерфейс, используемый внешнее свойство шрифт контейнера.

Если *pFontDispAmbient* является NULL, новый шрифт создания объекта из описание шрифта, на которые указывают *pFontDesc* или, если *pFontDesc* имеет значение NULL, из значения по умолчанию Описание.

Вызывайте эту функцию после построения `CFontHolder` объекта.

##  <a name="m_pfont"></a>  CFontHolder::m_pFont

Указатель на `CFontHolder` объекта `IFont` интерфейс.

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics

Возвращает данные для физического шрифта, представленного `CFontHolder` объекта.

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>Параметры

*lptm*<br/>
Указатель на [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) структуру, которая будет получать сведения.

##  <a name="releasefont"></a>  CFontHolder::ReleaseFont

Эта функция отключается `CFontHolder` объекта из его `IFont` интерфейс.

```
void ReleaseFont();
```

##  <a name="select"></a>  CFontHolder::Select

Вызывайте эту функцию, чтобы выбрать шрифт элемента управления в заданном контексте устройства.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Параметры

*основного контроллера домена*<br/>
Контекст устройства, в котором выбран шрифт.

*cyLogical*<br/>
Высота в логических единицах прямоугольника, в которой рисуется элемент управления.

*cyHimetric*<br/>
Высота в единицах MM_HIMETRIC, элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на шрифт, который требуется заменить.

### <a name="remarks"></a>Примечания

См. в разделе [GetFontHandle](#getfonthandle) обсуждение *cyLogical* и *cyHimetric* параметров.

##  <a name="setfont"></a>  CFontHolder::SetFont

Освобождает любой существующий шрифт и подключается `CFontHolder` объект `IFont` интерфейс.

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>Параметры

*pNewFont*<br/>
Указатель на новый `IFont` интерфейс.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPropExchange](../../mfc/reference/cpropexchange-class.md)
