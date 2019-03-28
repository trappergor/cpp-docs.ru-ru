---
title: Класс CD2DTextLayout
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: ca89d12c6aeed33be740aa9f999e7c11d6c32056
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565273"
---
# <a name="cd2dtextlayout-class"></a>Класс CD2DTextLayout

Оболочка для IDWriteTextLayout.

## <a name="syntax"></a>Синтаксис

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Создает объект CD2DTextLayout.|
|[CD2DTextLayout:: ~ CD2DTextLayout](#_dtorcd2dtextlayout)|Деструктор Вызывается при уничтожении объекта макета текста D2D.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CD2DTextLayout::Create](#create)|Создает CD2DTextLayout. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::destroy](#destroy)|Уничтожает объект CD2DTextLayout. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout::Get](#get)|Возвращает интерфейс IDWriteTextLayout|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Копирует имя семейства шрифтов текста в указанной позиции.|
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Возвращает имя языкового стандарта текста в указанной позиции.|
|[CD2DTextLayout::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextLayout::ReCreate](#recreate)|Повторно создает CD2DTextLayout. (Переопределяет [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Имя семейства шрифтов, завершающаяся нулем наборов для текста в указанный текстовый диапазон|
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Задает имя языкового стандарта для текста в указанный текстовый диапазон|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CD2DTextLayout::operator IDWriteTextLayout*](#operator_idwritetextlayout_star)|Возвращает интерфейс IDWriteTextLayout|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|Указатель на IDWriteTextLayout.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="_dtorcd2dtextlayout"></a>  CD2DTextLayout::~CD2DTextLayout

Деструктор Вызывается при уничтожении объекта макета текста D2D.

```
virtual ~CD2DTextLayout();
```

##  <a name="cd2dtextlayout"></a>  CD2DTextLayout::CD2DTextLayout

Создает объект CD2DTextLayout.

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на целевой объект отрисовки.

*strText*<br/>
Объект CString, содержащий строку, чтобы создать новый объект CD2DTextLayout из.

*TextFormat*<br/>
Объект CString, содержащий формат, применяемый к строке.

*sizeMax*<br/>
Размер окна макета.

*bAutoDestroy*<br/>
Указывает, что объект будет уничтожен владельца (pParentTarget).

##  <a name="create"></a>  CD2DTextLayout::Create

Создает CD2DTextLayout.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="destroy"></a>  CD2DTextLayout::destroy

Уничтожает объект CD2DTextLayout.

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextLayout::Get

Возвращает интерфейс IDWriteTextLayout

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IDWriteTextLayout или значение NULL, если объект еще не инициализирован.

##  <a name="getfontfamilyname"></a>  CD2DTextLayout::GetFontFamilyName

Копирует имя семейства шрифтов текста в указанной позиции.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Параметры

*currentPosition*<br/>
Позиция текст для проверки.

*TextRange*<br/>
Диапазон текста, который имеет то же форматирование текста в позиции, заданной параметром currentPosition. Это означает, что запуск имеет точный как позиции, указанной в, включая, но не ограничиваясь имя семейства шрифтов.

### <a name="return-value"></a>Возвращаемое значение

Объект CString, содержащий текущее имя семейства шрифтов.

##  <a name="getlocalename"></a>  CD2DTextLayout::GetLocaleName

Возвращает имя языкового стандарта текста в указанной позиции.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Параметры

*currentPosition*<br/>
Положение текста для проверки.

*TextRange*<br/>
Диапазон текста, который имеет то же форматирование текста в позиции, заданной параметром currentPosition. Это означает, что запуск имеет точный как позиции, указанной в, включая, но не ограничиваясь имени языкового стандарта.

### <a name="return-value"></a>Возвращаемое значение

Объект CString, содержащий имя текущего языкового стандарта.

##  <a name="isvalid"></a>  CD2DTextLayout::IsValid

Проверяет допустимость ресурсов

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.

##  <a name="m_ptextlayout"></a>  CD2DTextLayout::m_pTextLayout

Указатель на IDWriteTextLayout.

```
IDWriteTextLayout* m_pTextLayout;
```

##  <a name="operator_idwritetextlayout_star"></a>  CD2DTextLayout::operator IDWriteTextLayout*

Возвращает интерфейс IDWriteTextLayout

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IDWriteTextLayout или значение NULL, если объект еще не инициализирован.

##  <a name="recreate"></a>  CD2DTextLayout::ReCreate

Повторно создает CD2DTextLayout.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="setfontfamilyname"></a>  CD2DTextLayout::SetFontFamilyName

Имя семейства шрифтов, завершающаяся нулем наборов для текста в указанный текстовый диапазон

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Параметры

*pwzFontFamilyName*<br/>
Имя семейства шрифтов, к которому применяется всей строки текста в диапазоне, определяемом textRange

*TextRange*<br/>
Текстовый диапазон, к которому относится это изменение

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE

##  <a name="setlocalename"></a>  CD2DTextLayout::SetLocaleName

Задает имя языкового стандарта для текста в указанный текстовый диапазон

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Параметры

*pwzLocaleName*<br/>
Строка имени языкового стандарта, завершающаяся нулем

*TextRange*<br/>
Текстовый диапазон, к которому относится это изменение

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
