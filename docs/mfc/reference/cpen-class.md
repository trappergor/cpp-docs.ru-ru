---
title: Cpen-класс
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: 8510c29571e6a370c7948ebe49e53b2c22dbfb9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372924"
---
# <a name="cpen-class"></a>Cpen-класс

Инкапсулирует перо интерфейса графических устройств Windows (GDI).

## <a name="syntax"></a>Синтаксис

```
class CPen : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPen::CPen](#cpen)|Создает объект `CPen`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPen::CreatePen](#createpen)|Создает логический перо финальных или геометрическом с указанного стиля, ширины и атрибуты кисти и присоединяет его к `CPen` объекта.|
|[CPen::CreatePenIndirect](#createpenindirect)|Создает перо с стиль, ширину и цвет, заданный в [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) структурировать и присоединяет его к `CPen` объекта.|
|[CPen::FromHandle](#fromhandle)|Возвращает указатель на `CPen` объект для заданного Windows HPEN.|
|[CPen::GetExtLogPen](#getextlogpen)|Получает [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) базовой структуры.|
|[CPen::GetLogPen](#getlogpen)|Получает [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) базовой структуры.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CPen::operator HPEN](#operator_hpen)|Возвращает дескриптор Windows, подключенный к `CPen` объекта.|

## <a name="remarks"></a>Примечания

Дополнительные сведения об использовании `CPen`, см. в разделе [графические объекты](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cpen"></a>  CPen::CPen

Создает объект `CPen`.

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Параметры

*nPenStyle*<br/>
Задает стиль пера. Этот параметр в первой версии конструктора может принимать одно из следующих значений:

- PS_SOLID создает сплошной перо.

- PS_DASH создает штрихового пера. Данный параметр является допустимым, только в том случае, если перо ширина равна 1 или менее, в устройстве единиц.

- PS_DOT создает точечно перо. Данный параметр является допустимым, только в том случае, если перо ширина равна 1 или менее, в устройстве единиц.

- Создает PS_DASHDOT пера с чередованием дефисы и точки. Данный параметр является допустимым, только в том случае, если перо ширина равна 1 или менее, в устройстве единиц.

- PS_DASHDOTDOT создает a перо сменяющих друг друга штрихов и double точек. Данный параметр является допустимым, только в том случае, если перо ширина равна 1 или менее, в устройстве единиц.

- PS_NULL создает null перо.

- PS_INSIDEFRAME создает созданных перо, рисующее строку в фрейме замкнутые фигуры в Windows GDI выходные данные функции, определяющие ограничивающий прямоугольник (например, `Ellipse`, `Rectangle`, `RoundRect`, `Pie`и `Chord`функции-члены). При использовании этого стиля с помощью функций Windows GDI выходные данные, которые задают ограничивающий прямоугольник (например, `LineTo` функция-член), области рисования пера не ограничивается кадр.

Вторая версия `CPen` конструктор задает сочетание тип, стиль, конечного элемента и атрибуты соединения. Значения из каждой категории следует использовать в сочетании с помощью битового оператора или (&#124;). Тип пера может принимать одно из следующих значений:

- PS_GEOMETRIC создает геометрический перо.

- PS_COSMETIC создает финальных перо.

   Вторая версия `CPen` конструктор добавляет следующие стили пера для *nPenStyle*:

- PS_ALTERNATE создает перо, задает все пикселы. (Этот стиль применяется только к финальных перья.)

- Создает PS_USERSTYLE перо, использует массив стилей предоставленные пользователем.

   Конечного элемента может принимать одно из следующих значений:

- PS_ENDCAP_ROUND оконечных round.

- PS_ENDCAP_SQUARE оконечных square.

- PS_ENDCAP_FLAT оконечных фиксированы.

   Соединение может принимать одно из следующих значений:

- Присоединяет PS_JOIN_BEVEL являются скошенные.

- Присоединяет PS_JOIN_MITER являются углом внутри текущего предельного значения, указываемого [SetMiterLimit](/windows/desktop/api/wingdi/nf-wingdi-setmiterlimit) функции. Если соединение превышает этот предел, скошенные его.

- Присоединяет PS_JOIN_ROUND round.

*nWidth*<br/>
Задает ширину пера.

- Для первой версии конструктора Если это значение равно 0, ширина в единицах устройства всегда равно 1 пиксель, независимо от режима сопоставления.

- Для второй версии конструктора Если *nPenStyle* является PS_GEOMETRIC, ширина предоставляется в логических единицах. Если *nPenStyle* является PS_COSMETIC, ширина должно быть установлено в 1.

*crColor*<br/>
Содержит цвета в формате RGB для пера.

*pLogBrush*<br/>
Указывает на `LOGBRUSH` структуры. Если *nPenStyle* является PS_COSMETIC, *lbColor* членом `LOGBRUSH` структура определяет цвет пера и *lbStyle* членом `LOGBRUSH` Структура должно быть присвоено BS_SOLID. Если *nPenStyle* является PS_GEOMETRIC, все члены должен использоваться для указания атрибутов кисть пера.

*nStyleCount*<br/>
Задает длину в единицах двойного слова из *lpStyle* массива. Это значение должно быть равно нулю, если *nPenStyle* не PS_USERSTYLE.

*lpStyle*<br/>
Указывает массив значений двойного слова. Первое значение указывает длину первый дефис в пользовательский стиль, второе значение указывает длину первое пространство и т. д. Этот указатель должен иметь значение NULL, если *nPenStyle* не PS_USERSTYLE.

### <a name="remarks"></a>Примечания

Если вы используете конструктор без аргументов, необходимо инициализировать результирующий `CPen` со `CreatePen`, `CreatePenIndirect`, или `CreateStockObject` функций-членов.

Если вы используете конструктор, принимающий аргументы, Дополнительная инициализация не требуется. Конструктор аргументов может создавать исключения, если ошибки обнаружены, пока конструктор без аргументов, всегда будет успешной.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

##  <a name="createpen"></a>  CPen::CreatePen

Создает логический перо финальных или геометрическом с указанного стиля, ширины и атрибуты кисти и присоединяет его к `CPen` объекта.

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Параметры

*nPenStyle*<br/>
Задает стиль для пера. Список возможных значений см. в разделе *nPenStyle* параметр в [CPen](#cpen) конструктор.

*nWidth*<br/>
Задает ширину пера.

- Для первой версии `CreatePen`, если это значение равно 0, ширина в единицах устройства всегда равна 1 пиксель, независимо от режима сопоставления.

- Для второй версии `CreatePen`, если *nPenStyle* является PS_GEOMETRIC, ширина предоставляется в логических единицах. Если *nPenStyle* является PS_COSMETIC, ширина должно быть установлено в 1.

*crColor*<br/>
Содержит цвета в формате RGB для пера.

*pLogBrush*<br/>
Указывает на [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) структуры. Если *nPenStyle* является PS_COSMETIC, `lbColor` членом `LOGBRUSH` структура определяет цвет пера и *lbStyle* членом `LOGBRUSH` структуры должно быть присвоено BS_ СПЛОШНОЙ. Если nPenStyle PS_GEOMETRIC, все члены должны использоваться для указания атрибутов кисть пера.

*nStyleCount*<br/>
Задает длину в единицах двойного слова из *lpStyle* массива. Это значение должно быть равно нулю, если *nPenStyle* не PS_USERSTYLE.

*lpStyle*<br/>
Указывает массив значений двойного слова. Первое значение указывает длину первый дефис в пользовательский стиль, второе значение указывает длину первое пространство и т. д. Этот указатель должен иметь значение NULL, если *nPenStyle* не PS_USERSTYLE.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешно, или нуль, если происходит сбой метода.

### <a name="remarks"></a>Примечания

Первая версия `CreatePen` инициализирует пера с указанный стиль, ширину и цвет. Перо может быть впоследствии выбран в качестве текущего пера для любого контекста устройства.

Перья, имеющих больше 1 пиксель ширину должны всегда иметь PS_NULL, PS_SOLID или PS_INSIDEFRAME стиля.

Если перо PS_INSIDEFRAME стиль и цвет, который не соответствует цвета в таблице логических цветов, пера рисуется пером сглаженный цвет. Стиль пера PS_SOLID не может использоваться для создания с сглаженный цвет пера. Стиль PS_INSIDEFRAME идентична PS_SOLID, если ширина пера меньше или равно 1.

Вторая версия `CreatePen` инициализирует логические финальных или геометрическом пера, для которого задан стиль, ширину и кисти атрибуты. Ширина пера финальных всегда равно 1; Ширина пера геометрические всегда указывается в мировых единицах. После того как приложение создаст логические пера, он может выбрать этого пера в контексте устройства, вызвав [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функции. После выбора пера в контексте устройства используется для рисования линий и кривых.

- Если *nPenStyle* PS_COSMETIC и PS_USERSTYLE, записи в *lpStyle* массива укажите длину штрихов и пробелов в единицах стиля. Стиль определяются устройства, в котором перо, которое используется для рисования линии.

- Если *nPenStyle* PS_GEOMETRIC и PS_USERSTYLE, записи в *lpStyle* массива укажите длину штрихов и пробелов в логических единицах.

- Если *nPenStyle* PS_ALTERNATE, единицы стиль игнорируется и все пикселы.

Если приложение больше не требуется данного пера, он должен вызывать [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) члена функции или уничтожать `CPen` объекта, поэтому ресурс больше не используется. Приложения не следует удалять пера, при выборе в контексте устройства пера.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect

Инициализирует перо, имеет стиль, ширину и цвет, заданный в структуре, на которые указывают *lpLogPen*.

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>Параметры

*lpLogPen*<br/>
Указывает Windows [LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen) структуру, содержащую сведения о пера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Перья, имеющих больше 1 пиксель ширину должны всегда иметь PS_NULL, PS_SOLID или PS_INSIDEFRAME стиля.

Если перо PS_INSIDEFRAME стиль и цвет, который не соответствует цвета в таблице логических цветов, пера рисуется пером сглаженный цвет. Стиль PS_INSIDEFRAME идентична PS_SOLID, если ширина пера меньше или равно 1.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

##  <a name="fromhandle"></a>  CPen::FromHandle

Возвращает указатель на `CPen` объект, заданный дескриптор для объекта pen Windows GDI.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>Параметры

*hPen*<br/>
`HPEN` Дескриптор Windows GDI пера.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CPen` объекта, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если объект `CPen` не прикреплен к дескриптору, создается и прикрепляется временный объект `CPen`. Этот временный `CPen` объект является допустимым, только пока очередном приложение время простоя в свой цикл событий, после чего график все временные объекты будут удалены. Другими словами временный объект используется только во время обработки сообщения одного окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

##  <a name="getextlogpen"></a>  CPen::GetExtLogPen

Получает `EXTLOGPEN` базовой структуры.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>Параметры

*pLogPen*<br/>
Указывает на [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) структуру, содержащую сведения о пера.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`EXTLOGPEN` Структура определяет стиль, ширину и атрибуты кисть пера. Например, вызвать `GetExtLogPen` в соответствии со стилем конкретного пера.

В следующих разделах в пакете SDK для Windows, сведения об атрибутах пера:

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

- [ExtCreatePen](/windows/desktop/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>Пример

В следующем примере кода показан вызов `GetExtLogPen` для извлечения атрибутов с помощью пера, а затем создать новый, финальных пера с тем же цветом.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

##  <a name="getlogpen"></a>  CPen::GetLogPen

Получает `LOGPEN` базовой структуры.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>Параметры

*pLogPen*<br/>
Указывает на [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) структуру, содержащую сведения о пера.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`LOGPEN` Структура определяет стиль, цвет и шаблон пера.

Например, вызвать `GetLogPen` в соответствии со стилем конкретного пера.

В следующих разделах в пакете SDK для Windows, сведения об атрибутах пера:

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

### <a name="example"></a>Пример

В следующем примере кода показан вызов `GetLogPen` для получения символа пера, а затем создайте пера новый, сплошной цвет.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

##  <a name="operator_hpen"></a>  CPen::operator HPEN

Возвращает дескриптор Windows GDI присоединенного `CPen` объекта.

```
operator HPEN() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если в случае успешного выполнения дескриптор объекта Windows GDI, представленных `CPen` объекта; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Этот оператор — оператор приведения, который поддерживает непосредственное использование объекта HPEN.

Дополнительные сведения об использовании графических объектов см. в статье [объектов график](/windows/desktop/gdi/graphic-objects) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>См. также

[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CBrush](../../mfc/reference/cbrush-class.md)
