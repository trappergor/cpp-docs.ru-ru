---
title: Класс CD2DTextFormat
ms.date: 03/27/2019
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: f7310fd3ca2ac34df7cc1a99cd5527ea8ba709c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369037"
---
# <a name="cd2dtextformat-class"></a>Класс CD2DTextFormat

Обертка для IDWriteTextFormat.

## <a name="syntax"></a>Синтаксис

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|Строит объект CD2DTextFormat.|
|[CD2DTextFormat:: »CD2DTextFormat](#_dtorcd2dtextformat)|Деструктор Вызывается при уничтожении объекта формата текста D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DTextFormat::Создание](#create)|Создает CD2DTextFormat. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextФормат: :Dэсстрой](#destroy)|Уничтожает объект CD2DTextFormat. (Переопределяет [CD2DРесурс::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextФормат::Получить](#get)|Возвращает интерфейс IDWriteTextFormat|
|[CD2DTextФормат::GetFontFamilyName](#getfontfamilyname)|Получает копию фамилии шрифта.|
|[CD2DTextФормат::GetLocaleName](#getlocalename)|Получает копию названия локализовать.|
|[CD2DTextFormat::IsValid](#isvalid)|Проверка достоверности ресурса (Переопределения [CD2DРесурса:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextФормат::Воссоздание](#recreate)|Воссоздает CD2DTextFormat. (Переопределяет [CD2DРесурс::Воссоздание](../../mfc/reference/cd2dresource-class.md#recreate).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DTextFormat:оператор IDWriteTextFormat](#operator_idwritetextformat_star)|Возвращает интерфейс IDWriteTextFormat|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DTextФормат::m_pTextFormat](#m_ptextformat)|Указатель на IDWriteTextFormat.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

[CD2DTextФормат](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a>CD2DTextFormat:: »CD2DTextFormat

Деструктор Вызывается при уничтожении объекта формата текста D2D.

```
virtual ~CD2DTextFormat();
```

## <a name="cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a>CD2DTextFormat::CD2DTextFormat

Строит объект CD2DTextFormat.

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*strFontFamilyName*<br/>
Объект CString, содержащий имя семейства шрифтов.

*Fontsize*<br/>
Логический размер шрифта в единицах DIP ("устройство-независимый пиксель"). DIPequals 1/96 дюйма.

*Fontweight*<br/>
Значение, указывававое вес шрифта для объекта текста.

*Fontstyle*<br/>
Значение, указывававое стиле шрифта для объекта текста.

*Fontstretch*<br/>
Значение, указывававое растяжение шрифта для объекта текста.

*strFontLocale*<br/>
Объект CString, содержащий имя ломыка.

*pFontCollection*<br/>
Указатель на объект сбора шрифтов. Когда это NULL, указывает на сбор шрифтов системы.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dtextformatcreate"></a><a name="create"></a>CD2DTextFormat::Создание

Создает CD2DTextFormat.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dtextformatdestroy"></a><a name="destroy"></a>CD2DTextФормат: :Dэсстрой

Уничтожает объект CD2DTextFormat.

```
virtual void Destroy();
```

## <a name="cd2dtextformatget"></a><a name="get"></a>CD2DTextФормат::Получить

Возвращает интерфейс IDWriteTextFormat

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IDWriteTextFormat или NULL, если объект еще не инициализирован.

## <a name="cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2DTextФормат::GetFontFamilyName

Получает копию фамилии шрифта.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект CString, содержащий текущую фамилию шрифта.

## <a name="cd2dtextformatgetlocalename"></a><a name="getlocalename"></a>CD2DTextФормат::GetLocaleName

Получает копию названия локализовать.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект CString, содержащий текущее имя локализу.

## <a name="cd2dtextformatisvalid"></a><a name="isvalid"></a>CD2DTextFormat::IsValid

Проверка достоверности ресурса

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dtextformatm_ptextformat"></a><a name="m_ptextformat"></a>CD2DTextФормат::m_pTextFormat

Указатель на IDWriteTextFormat.

```
IDWriteTextFormat* m_pTextFormat;
```

## <a name="cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a>CD2DTextFormat:оператор IDWriteTextFormat

Возвращает интерфейс IDWriteTextFormat

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IDWriteTextFormat или NULL, если объект еще не инициализирован.

## <a name="cd2dtextformatrecreate"></a><a name="recreate"></a>CD2DTextФормат::Воссоздание

Воссоздает CD2DTextFormat.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
