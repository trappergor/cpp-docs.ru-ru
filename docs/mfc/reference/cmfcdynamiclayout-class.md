---
title: Класс CMFCDynamicLayout
ms.date: 11/04/2016
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
ms.openlocfilehash: 40dedbe2737a79b7531b8acd47870ce7cb788604
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288406"
---
# <a name="cmfcdynamiclayout-class"></a>Класс CMFCDynamicLayout

Определяет порядок перемещения и изменения размеров элементов управления при изменении размеров окна.

## <a name="syntax"></a>Синтаксис

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|Создает объект `CMFCDynamicLayout`.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).|
|[CMFCDynamicLayout::Adjust](#adjust)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).|
|[CMFCDynamicLayout::Create](#create)|Хранит и проверяет главное окно.|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Возвращает указатель на главное окно.|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Возвращает минимальный размер окна для макета.|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Извлекает прямоугольник для текущей клиентской области окна.|
|[CMFCDynamicLayout::HasItem](#hasitem)|Проверяет, добавлялся ли дочерний элемент управления в динамический макет.|
|[CMFCDynamicLayout::IsEmpty](#isempty)|Проверяет, что в динамический макет не добавлялись дочерние окна.|
|[CMFCDynamicLayout::LoadResource](#loadresource)|Считывает динамический макет из ресурса AFX_DIALOG_LAYOUT и применяет его для главного окна.|
|статические [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Получает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера его главного окна.|
|статические [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Получает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера его главного окна.|
|статические [CMFCDynamicLayout::MoveNone](#movenone)|Получает [MoveSettings](#movesettings_structure) значение, представляющее движение не вертикальной или горизонтальной для дочернего элемента управления.|
|статические [CMFCDynamicLayout::MoveVertical](#movevertical)|Получает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера его главного окна.|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Задает минимальный размер окна для макета.|
|статические [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Получает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочерний элемент управления является размер по горизонтали при изменении пользователем размера его главного окна.|
|статические [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|Получает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочерний элемент управления является размер по горизонтали при изменении пользователем размера его главного окна.|
|статические [CMFCDynamicLayout::SizeNone](#sizenone)|Получает [SizeSettings](#sizesettings_structure) значение, соответствующее нулевому изменению размера дочернего элемента управления.|
|статические [CMFCDynamicLayout::SizeVertical](#sizevertical)|Получает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления изменяется по вертикали при изменении пользователем размера его главного окна.|

## <a name="nested-types"></a>Вложенные типы

|name|Описание:|
|----------|-----------------|
|[Структура CMFCDynamicLayout::MoveSettings](#movesettings_structure)|Инкапсулирует данные перемещения для элементов управления в динамическом макете.|
|[Структура CMFCDynamicLayout::SizeSettings](#sizesettings_structure)|Инкапсулирует данные об изменении размера элементов управления в динамическом макете.|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxlayout.h

##  <a name="additem"></a>  CMFCDynamicLayout::AddItem

Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>Параметры

*hwnd*<br/>
Дескриптор добавляемого окна.

*nID*<br/>
Идентификатор добавляемого дочернего элемента управления.

*moveSettings*<br/>
Структура, описывающая перемещение элемента управления при изменении размера окна.

*sizeSettings*<br/>
Структура, описывающая изменение размера элемента управления при изменении размера окна.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент был успешно добавлен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна.

##  <a name="adjust"></a>  CMFCDynamicLayout::Adjust

Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно (обычно элемент управления).

```
void Adjust();
```

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна.

##  <a name="create"></a>  CMFCDynamicLayout::Create

Хранит и проверяет главное окно.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>Параметры

*pHostWnd*<br/>
Указатель на главное окно.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если создание прошло успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="gethostwnd"></a>  CMFCDynamicLayout::GetHostWnd

Возвращает указатель на главное окно.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на главное окно.

### <a name="remarks"></a>Примечания

По умолчанию положения всех дочерних элементов управления пересчитываются относительно этого окна. 

##  <a name="getminsize"></a>  CMFCDynamicLayout::GetMinSize

Возвращает минимальный размер окна для макета.

```
CSize GetMinSize();
```

### <a name="return-value"></a>Возвращаемое значение

Минимальный размер окна для макета.

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна, однако существует минимальный допустимый размер для макета. Пользователь может сделать окно меньше этого значения, но тогда определенные части окна будут скрыты.

##  <a name="getwindowrect"></a>  CMFCDynamicLayout::GetWindowRect

Извлекает прямоугольник для текущей клиентской области окна.

```
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
После возвращения функцией этот параметр содержит ограничивающий прямоугольник области макета. Это выходной параметр. Входное значение перезаписывается.

### <a name="remarks"></a>Примечания

##  <a name="hasitem"></a>  CMFCDynamicLayout::HasItem

Проверяет, добавлялся ли дочерний элемент управления в динамический макет.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>Параметры

*hwnd*<br/>
Дескриптор окна для элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если макет уже содержит данный элемент; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="isempty"></a>  CMFCDynamicLayout::IsEmpty

Проверяет, что в динамический макет не добавлялись дочерние окна.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если макет не содержит элементов; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="loadresource"></a>  CMFCDynamicLayout::LoadResource

Считывает динамический макет из ресурса AFX_DIALOG_LAYOUT и применяет его для главного окна.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>Параметры

*pHostWnd*<br/>
Указатель на главное окно.

*lpResource*<br/>
Указатель на буфер, содержащий ресурс AFX_DIALOG_LAYOUT.

*dwSize*<br/>
Размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ресурс загружен и применен для главного окна; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="movehorizontal"></a>  CMFCDynamicLayout::MoveHorizontal

Получает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера его главного окна.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>Параметры

*nRatio*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Объект [MoveSettings](#movesettings_structure) значение, инкапсулирующее запрашиваемое отношение при перемещении.

### <a name="remarks"></a>Примечания

##  <a name="movehorizontalandvertical"></a>  CMFCDynamicLayout::MoveHorizontalAndVertical

Получает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера его главного окна.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Параметры

*nXRatio*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.

*nYRatio*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Объект [MoveSettings](#movesettings_structure) значение, инкапсулирующее запрашиваемое отношение при перемещении.

### <a name="remarks"></a>Примечания

##  <a name="movenone"></a>  CMFCDynamicLayout::MoveNone

Получает [MoveSettings](#movesettings_structure) значение, представляющее движение не вертикальной или горизонтальной для дочернего элемента управления.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [MoveSettings](#movesettings_structure) значение, фиксирующее элемент управления на месте, таким образом, чтобы он не перемещался при изменении пользователем размера главного окна.

### <a name="remarks"></a>Примечания

##  <a name="movesettings_structure"></a>  Структура CMFCDynamicLayout::MoveSettings

Инкапсулирует данные перемещения для элементов управления в динамическом макете.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>Примечания

Этот класс является вложенным в `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal

Проверяет, задано ли в данных перемещения ненулевое перемещение по горизонтали.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `MoveSettings` задает ненулевое перемещение по горизонтали.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone

Проверяет, что задано нулевое перемещение данных.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `MoveSettings` задает нулевое перемещение.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical

  Проверяет, задано ли в данных перемещения ненулевое перемещение по вертикали.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `MoveSettings` задает ненулевое перемещение по вертикали.

##  <a name="movevertical"></a>  CMFCDynamicLayout::MoveVertical

Получает [MoveSettings](#movesettings_structure) значение, которое определяет, сколько дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера его главного окна.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>Параметры

*nRatio*<br/>
Определяет расстояние (в процентах), на которое дочерний элемент управления будет перемещаться по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Объект [MoveSettings](#movesettings_structure) значение, инкапсулирующее запрашиваемое отношение при перемещении.

### <a name="remarks"></a>Примечания

##  <a name="setminsize"></a>  CMFCDynamicLayout::SetMinSize

Задает минимальный размер окна для макета.

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Необходимый минимальный размер макета.

### <a name="remarks"></a>Примечания

Положение и размер дочернего элемента управления динамически меняются при изменении размера главного окна, однако существует минимальный допустимый размер для макета. Пользователь может сделать окно меньше этого значения, но тогда определенные части окна будут скрыты.

##  <a name="sizehorizontal"></a>  CMFCDynamicLayout::SizeHorizontal

Получает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочерний элемент управления является размер по горизонтали при изменении пользователем размера его главного окна.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>Параметры

*nRatio*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по горизонтали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Объект [SizeSettings](#sizesettings_structure) значение, которое инкапсулирует запрашиваемое отношение размеров.

### <a name="remarks"></a>Примечания

##  <a name="sizehorizontalandvertical"></a>  CMFCDynamicLayout::SizeHorizontalAndVertical

Получает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочерний элемент управления является размер по горизонтали при изменении пользователем размера его главного окна.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Параметры

*nXRatio*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по горизонтали при изменении пользователем размера главного окна.

*nYRatio*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Объект [SizeSettings](#sizesettings_structure) значение, которое инкапсулирует запрашиваемое отношение размеров.

### <a name="remarks"></a>Примечания

##  <a name="sizenone"></a>  CMFCDynamicLayout::SizeNone

Получает [SizeSettings](#sizesettings_structure) значение, соответствующее нулевому изменению размера дочернего элемента управления.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [SizeSettings](#sizesettings_structure) значение, которое устраняет элемента управления в определенный размер, таким образом, чтобы он не изменяет размер при изменении пользователем размера главного окна.

### <a name="remarks"></a>Примечания

##  <a name="sizesettings_structure"></a>  Структура CMFCDynamicLayout::SizeSettings

Инкапсулирует данные об изменении размера элементов управления в динамическом макете.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>Примечания

Этот класс является вложенным в `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal

Проверяет, задано ли в данных об изменении размера ненулевое изменение размера по горизонтали.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `SizeSettings` задает ненулевое изменение размера по горизонтали.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone

Проверяет, задано ли в данных об изменении размера нулевое изменение размера.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `SizeSettings` задает нулевое изменение размера.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical

Проверяет, задано ли в данных об изменении размера ненулевое изменение размера по вертикали.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если объект `SizeSettings` задает ненулевое изменение размера по вертикали.

##  <a name="sizevertical"></a>  CMFCDynamicLayout::SizeVertical

Получает [SizeSettings](#sizesettings_structure) значение, которое определяет, сколько дочернего элемента управления изменяется по вертикали при изменении пользователем размера его главного окна.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>Параметры

*nRatio*<br/>
Определяет в процентах, как будет меняться размер дочернего элемента управления по вертикали при изменении пользователем размера главного окна.

### <a name="return-value"></a>Возвращаемое значение

Объект [SizeSettings](#sizesettings_structure) значение, которое инкапсулирует запрашиваемое отношение размеров.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
