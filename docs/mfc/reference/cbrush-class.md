---
title: Класс CBrush
ms.date: 11/04/2016
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
ms.openlocfilehash: 38f9c6953999e07f1a72ed6a9c0661184f075ea0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303083"
---
# <a name="cbrush-class"></a>Класс CBrush

Инкапсулирует кисть интерфейса графических устройств Windows (GDI).

## <a name="syntax"></a>Синтаксис

```
class CBrush : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CBrush::CBrush](#cbrush)|Создает объект `CBrush`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Инициализирует кисти с стиль, цвет и шаблону, заданному в [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) структуры.|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Инициализирует кисти с шаблону, указанному аппаратно независимый точечный рисунок (DIB).|
|[CBrush::CreateHatchBrush](#createhatchbrush)|Инициализирует кисти с указанным заштрихованный шаблон и цветом.|
|[CBrush::CreatePatternBrush](#createpatternbrush)|Инициализирует кисти с шаблону, указанному растрового изображения.|
|[CBrush::CreateSolidBrush](#createsolidbrush)|Инициализирует кисти с указанным сплошным цветом.|
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Создает кисть, которая является системный цвет по умолчанию.|
|[CBrush::FromHandle](#fromhandle)|Возвращает указатель на `CBrush` объект для заданного дескриптора для Windows `HBRUSH` объекта.|
|[CBrush::GetLogBrush](#getlogbrush)|Получает [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) структуры.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[HBRUSH CBrush::operator](#operator_hbrush)|Возвращает дескриптор Windows, подключенный к `CBrush` объекта.|

## <a name="remarks"></a>Примечания

Для использования `CBrush` объекта, создания `CBrush` и передать его в любую `CDC` функция-член, требующий кисти.

Кисти может быть сплошная, hatched или узором.

Дополнительные сведения о `CBrush`, см. в разделе [графические объекты](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cbrush"></a>  CBrush::CBrush

Создает объект `CBrush`.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

*crColor*<br/>
Задает цвет переднего плана, кисти, как цвета в формате RGB. Если кисть hatched, этот параметр задает цвет штриховки.

*nIndex*<br/>
Задает стиль штриховки кисти. Он может принимать любое из следующих значений:

- HS_BDIAGONAL вниз штриховки (слева направо) на 45 градусов

- HS_CROSS горизонтальной и вертикальной клетчатый

- Диагональная HS_DIAGCROSS 45 градусов

- HS_FDIAGONAL вверх штриховки (слева направо) на 45 градусов

- HS_HORIZONTAL Горизонтальная штриховка

- Штриховка по вертикали HS_VERTICAL

*pBitmap*<br/>
Указывает на `CBitmap` , указывающий, с которым эта кисть рисует растровое изображение.

### <a name="remarks"></a>Примечания

`CBrush` четыре перегруженных конструктора. Конструктор без аргументов создает неинициализированный `CBrush` объект, который должен быть инициализирован, прежде чем можно будет использовать.

Если вы используете конструктор без аргументов, необходимо инициализировать результирующий `CBrush` со [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), или [CreateDIBPatternBrush](#createdibpatternbrush). Если вы используете один из конструкторов, принимающих аргументы, затем дальнейшая инициализация необходима. Конструкторы с аргументами может создавать исключения, если ошибки обнаружены, пока конструктор без аргументов, всегда будет успешной.

Конструктор с одним [COLORREF](/windows/desktop/gdi/colorref) параметр создает сплошной кисти с указанным цветом. Цвет указывает значение RGB и может быть создан с помощью макроса RGB в WINDOWS. З.

Конструктор с двумя параметрами кисть штриховки. *NIndex* параметр указывает индекс заштрихованный шаблон. *CrColor* параметр задает цвет.

Конструктор с `CBitmap` параметр кисть узором. Параметр определяет растрового изображения. Точечный рисунок предполагается, что были созданы с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [ CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). Минимальный размер растрового изображения для использования в узора заливки — 8 x 8 пикселей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

##  <a name="createbrushindirect"></a>  CBrush::CreateBrushIndirect

Инициализирует кисти с стиль, цвет и шаблону, заданному в [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) структуры.

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>Параметры

*lpLogBrush*<br/>
Указывает на [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) структуру, содержащую сведения о кисти.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Кисть, которая впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.

Кисть, созданных с помощью Монохромная (плоскость 1, 1 бит на пиксель) точечный рисунок рисуется с использованием текущих цветов текста и фона. Представленный немного присвоено значение 0 пикселей привязки будет рисоваться в текущий цвет текста. Точек представленной немного, равным 1 привязки будет рисоваться в текущий цвет фона.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

##  <a name="createdibpatternbrush"></a>  CBrush::CreateDIBPatternBrush

Инициализирует кисти с шаблону, указанному аппаратно независимый точечный рисунок (DIB).

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>Параметры

*hPackedDIB*<br/>
Определяет объект глобальной памяти, содержащего упакованное аппаратно независимых точечный рисунок (DIB).

*nUsage*<br/>
Указывает, является ли `bmiColors[]` поля [BITMAPINFO](/windows/desktop/api/wingdi/ns-wingdi-tagbitmapinfo) структуры данных (часть «упакованные DIB») содержать явные значения RGB или индексов в настоящее время реализованных логическую палитру. Параметр должен быть одним из следующих значений:

- DIB_PAL_COLORS таблица цветов содержит массив 16-разрядными индексами.

- DIB_RGB_COLORS таблица цветов содержит литеральные значения RGB.

*lpPackedDIB*<br/>
Указывает упакованный DIB, состоящий из `BITMAPINFO` структуру сразу следуют массив байтов, определение пиксели растрового изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть, которая впоследствии может быть выбран для любой контекст устройства, поддерживающей растровых операций.

Способ обработки DIB имеют две версии:

- В первой версии, чтобы получить дескриптор для файла DIB вызове Windows `GlobalAlloc` функцию, чтобы выделить блок глобальной памяти и затем заполнить память упакованный DIB.

- Во второй версии, нет необходимости вызывать `GlobalAlloc` выделить память для упакованного DIB.

Упакованный DIB состоит из `BITMAPINFO` структуру данных, непосредственно предшествовать массив байтов, определяющий пиксели растрового изображения. Растровых изображений, используемых как шаблоны заливки должны иметь размер 8 на 8 пикселей. Если размер растрового изображения, Windows создает шаблон заполнения, с помощью только биты, относящиеся к первые 8 строк и столбцов 8 пикселей в левом верхнем углу точечного рисунка.

Когда приложение выбирает шаблон кисти DIB двух цветов в контексте монохромный устройства, Windows игнорирует цвета, указанные в DIB, а вместо них отображается шаблон кисти с использованием текущих цветов текста и фона контекста устройства. Сопоставляется первый цвет (со смещением 0 в таблице цветов DIB) DIB пикселей отображаются с помощью цвета текста. Пиксели, сопоставляется со вторым цветом (со смещения 1 в таблице цветов), отображаются цветом фона.

Сведения об использовании следующих функций Windows см. в разделе Windows SDK:

- [CreateDIBPatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrush) (эта функция предназначена только для совместимости с приложениями, написанных для версий Windows, предшествующих версии 3.0; используйте `CreateDIBPatternBrushPt` функции.)

- [CreateDIBPatternBrushPt](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrushpt) (эта функция должна использоваться для приложений Win32.)

- [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

##  <a name="createhatchbrush"></a>  CBrush::CreateHatchBrush

Инициализирует кисти с указанным заштрихованный шаблон и цветом.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Задает стиль штриховки кисти. Он может принимать любое из следующих значений:

- HS_BDIAGONAL вниз штриховки (слева направо) на 45 градусов

- HS_CROSS горизонтальной и вертикальной клетчатый

- Диагональная HS_DIAGCROSS 45 градусов

- HS_FDIAGONAL вверх штриховки (слева направо) на 45 градусов

- HS_HORIZONTAL Горизонтальная штриховка

- Штриховка по вертикали HS_VERTICAL

*crColor*<br/>
Задает основной цвет кисти цветом RGB (Цвет штриховки). См. в разделе [COLORREF](/windows/desktop/gdi/colorref) в пакете SDK для Windows, Дополнительные сведения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть, которая впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

##  <a name="createpatternbrush"></a>  CBrush::CreatePatternBrush

Инициализирует кисти с шаблону, указанному растрового изображения.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

*pBitmap*<br/>
Идентифицирует растрового изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть, которая впоследствии может быть выбран для любой контекст устройства, поддерживающей растровых операций. Точечный рисунок, идентифицируемый *pBitmap* обычно инициализируются с помощью [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap:: LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), или [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) функции.

Растровых изображений, используемых как шаблоны заливки должны иметь размер 8 на 8 пикселей. Если размер растрового изображения, Windows будет использовать только биты, относящиеся к первые 8 строк и столбцов пикселей в левом верхнем углу точечного рисунка.

Шаблон кисти можно удалить без влияния на связанные растрового изображения. Это означает, что растрового изображения можно создать любое количество шаблон кисти.

Кисть, созданных с помощью монохромный точечный рисунок (1 цвет плоскости, 1 бит на пиксель) отображаются с помощью текущих цветов текста и фона. Представленный бит, равным 0 пикселов с текущего цвета текста. Представленный немного, равным 1 пикселов с текущим цветом фона.

Дополнительные сведения об использовании [CreatePatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createpatternbrush), Windows функции, см. в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

##  <a name="createsolidbrush"></a>  CBrush::CreateSolidBrush

Инициализирует кисти указанного сплошным цветом.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>Параметры

*crColor*<br/>
Объект [COLORREF](/windows/desktop/gdi/colorref) структуры, задающее цвет кисти. Цвет указывает значение RGB и может быть создан с помощью макроса RGB в WINDOWS. З.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть, которая впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.

Когда приложение будет завершено, с помощью кисти, созданные `CreateSolidBrush`, должен быть выбран кисть из контекста устройства.

### <a name="example"></a>Пример

  См. в примере [CBrush::CBrush](#cbrush).

##  <a name="createsyscolorbrush"></a>  CBrush::CreateSysColorBrush

Инициализирует цвета кисти.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Указывает индекс цветов. Это значение соответствует цвет, используемый для закрашивания один из элементов 21 окна. См. в разделе [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) в пакете Windows SDK для списка значений.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Кисть, которая впоследствии может быть выбран в качестве текущей кисти для любого контекста устройства.

Когда приложение будет завершено, с помощью кисти, созданные `CreateSysColorBrush`, должен быть выбран кисть из контекста устройства.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

##  <a name="fromhandle"></a>  CBrush::FromHandle

Возвращает указатель на `CBrush` объект для заданного дескриптора для Windows [HBRUSH](#operator_hbrush) объекта.

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>Параметры

*hBrush*<br/>
ДЕСКРИПТОР Windows GDI кисти.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CBrush` объекта, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если `CBrush` объект еще не присоединен к дескриптору, временный `CBrush` созданный и присоединенный объект. Этот временный `CBrush` объект действителен только до следующей встречи, в приложении есть время простоя в свой цикл событий. В настоящее время будут удалены все временные графические объекты. Другими словами временный объект допустим только во время обработки сообщения одного окна.

Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](/windows/desktop/gdi/graphic-objects) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CBrush::CBrush](#cbrush).

##  <a name="getlogbrush"></a>  CBrush::GetLogBrush

Вызовите эту функцию-член для извлечения `LOGBRUSH` структуры.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>Параметры

*pLogBrush*<br/>
Указывает на [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) структуру, содержащую сведения о кисти.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, и *pLogBrush* является допустимым указателем, возвращаемое значение — количество байтов, сохраненных в буфере.

Если функция выполняется успешно, и *pLogBrush* имеет значение NULL, возвращаемое значение — число байтов, необходимое для хранения информации, функция будет храниться в буфере.

Если функция завершается с ошибкой, то возвращаемое значение равно 0.

### <a name="remarks"></a>Примечания

`LOGBRUSH` Структура определяет стиль, цвет и шаблон кисти.

Например, вызвать `GetLogBrush` в соответствии с определенного цвета или узора растрового изображения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

##  <a name="operator_hbrush"></a>  HBRUSH CBrush::operator

Этот оператор используется для получения присоединенного дескриптор Windows GDI `CBrush` объекта.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если в случае успешного выполнения дескриптор объекта Windows GDI, представленных `CBrush` объекта; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Этот оператор — оператор приведения, который поддерживает непосредственное использование объекта HBRUSH.

Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](/windows/desktop/gdi/graphic-objects) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC PROPDLG](../../visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CBitmap](../../mfc/reference/cbitmap-class.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)
