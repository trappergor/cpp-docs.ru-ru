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
ms.openlocfilehash: 9be4c1134e2f82ceb3af31cbeb1a7d55f4071777
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369029"
---
# <a name="cd2dtextlayout-class"></a>Класс CD2DTextLayout

Обертка для IDWriteTextLayout.

## <a name="syntax"></a>Синтаксис

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Строит объект CD2DTextLayout.|
|[CD2DTextLayout: :»CD2DTextLayout](#_dtorcd2dtextlayout)|Деструктор Вызывается при уничтожении объекта макета текста D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DTextLayout::Создание](#create)|Создает CD2DTextLayout. (Переопределяет [CD2DРесурс::Создание](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::Destroy](#destroy)|Уничтожает объект CD2DTextLayout. (Переопределяет [CD2DРесурс::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout::Get](#get)|Возвращает интерфейс IDWriteTextLayout|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Копирует фамилию шрифта текста в указанном положении.|
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Получает название локализации текста в указанном положении.|
|[CD2DTextLayout::IsValid](#isvalid)|Проверка достоверности ресурса (Переопределения [CD2DРесурса:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextLayout::ReCreate](#recreate)|Воссоздает CD2DTextLayout. (Переопределяет [CD2DРесурс::Воссоздание](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Устанавливает фамилию недействительных шрифтов для текста в определенном текстовом диапазоне|
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Устанавливает название локализации для текста в определенном диапазоне текста|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DTextLayout:Оператор IDWriteTextLayout](#operator_idwritetextlayout_star)|Возвращает интерфейс IDWriteTextLayout|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|Указатель на IDWriteTextLayout.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CD2DРесурс](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a>CD2DTextLayout: :»CD2DTextLayout

Деструктор Вызывается при уничтожении объекта макета текста D2D.

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a>CD2DTextLayout::CD2DTextLayout

Строит объект CD2DTextLayout.

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
Указатель на цель рендера.

*strText*<br/>
Объект CString, содержащий строку для создания нового объекта CD2DTextLayout.

*textFormat*<br/>
Объект CString, содержащий формат для применения к строке.

*sizeMax*<br/>
Размер макетной коробки.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a>CD2DTextLayout::Создание

Создает CD2DTextLayout.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a>CD2DTextLayout::Destroy

Уничтожает объект CD2DTextLayout.

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a>CD2DTextLayout::Get

Возвращает интерфейс IDWriteTextLayout

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IDWriteTextLayout или NULL, если объект еще не инициализирован.

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2DTextLayout::GetFontFamilyName

Копирует фамилию шрифта текста в указанном положении.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Параметры

*текущаяПозиция*<br/>
Позиция текста для изучения.

*textRange*<br/>
Диапазон текста, который имеет тот же форматирование, что и текст в позиции, указанной currentPosition. Это означает, что запуск имеет точное форматирование, как указанное положение, включая, но не ограничиваясь фамилией шрифта.

### <a name="return-value"></a>Возвращаемое значение

Объект CString, содержащий текущую фамилию шрифта.

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a>CD2DTextLayout::GetLocaleName

Получает название локализации текста в указанном положении.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Параметры

*текущаяПозиция*<br/>
Положение текста для проверки.

*textRange*<br/>
Диапазон текста, который имеет тот же форматирование, что и текст в позиции, указанной currentPosition. Это означает, что запуск имеет точное форматирование, как указанное положение, включая, но не ограничиваясь названием ломык.

### <a name="return-value"></a>Возвращаемое значение

Объект CString, содержащий текущее имя локализу.

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a>CD2DTextLayout::IsValid

Проверка достоверности ресурса

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a>CD2DTextLayout::m_pTextLayout

Указатель на IDWriteTextLayout.

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a>CD2DTextLayout:Оператор IDWriteTextLayout

Возвращает интерфейс IDWriteTextLayout

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IDWriteTextLayout или NULL, если объект еще не инициализирован.

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a>CD2DTextLayout::ReCreate

Воссоздает CD2DTextLayout.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a>CD2DTextLayout::SetFontFamilyName

Устанавливает фамилию недействительных шрифтов для текста в определенном текстовом диапазоне

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Параметры

*pwzFontFamilyName*<br/>
Фамилия шрифта, которая применяется ко всей строке текста в диапазоне, указанном textRange

*textRange*<br/>
Диапазон текста, к которому относится это изменение

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a>CD2DTextLayout::SetLocaleName

Устанавливает название локализации для текста в определенном диапазоне текста

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Параметры

*pwzLocaleName*<br/>
Строка с нулевым именем локализового имени

*textRange*<br/>
Диапазон текста, к которому относится это изменение

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает TRUE. В противном случае, он возвращает FALSE

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
