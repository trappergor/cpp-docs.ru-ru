---
title: Класс CFont
ms.date: 11/04/2016
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
ms.openlocfilehash: 04136b3550675f0e50f905047fee551e27da7069
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182242"
---
# <a name="cfont-class"></a>Класс CFont

Инкапсулирует шрифт интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим шрифтом.

## <a name="syntax"></a>Синтаксис

```
class CFont : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CFont::CFont](#cfont)|Создает объект `CFont`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CFont::CreateFont](#createfont)|Инициализирует `CFont` с заданными характеристиками.|
|[CFont::CreateFontIndirect](#createfontindirect)|Инициализирует `CFont` объекта с параметрами, приведенными в `LOGFONT` структуры.|
|[CFont::CreatePointFont](#createpointfont)|Инициализирует `CFont` с высоты, измеряемый в десятых долях точки и начертания.|
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|Совпадение с кодом `CreateFontIndirect` за исключением того, что высота шрифта измеряется в десятых долях точку, а не в логических единицах.|
|[CFont::FromHandle](#fromhandle)|Возвращает указатель на `CFont` объект для заданного Windows HFONT.|
|[CFont::GetLogFont](#getlogfont)|Заполняет `LOGFONT` с информацией о шрифте, подключенный к `CFont` объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[HFONT CFont::operator](#operator_hfont)|Возвращает дескриптор шрифта Windows GDI подключен к `CFont` объекта.|

## <a name="remarks"></a>Примечания

Для использования `CFont` объекта, создания `CFont` объекта и присоединить к нему с помощью шрифта Windows [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), или [CreatePointFontIndirect](#createpointfontindirect), а затем с помощью функций-членов объектов для управления шрифта.

`CreatePointFont` И `CreatePointFontIndirect` функции часто являются проще в использовании, чем `CreateFont` или `CreateFontIndirect` так, как это преобразование для высоты шрифта от размера точки логических единиц автоматически.

Дополнительные сведения о `CFont`, см. в разделе [графические объекты](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cfont"></a>  CFont::CFont

Создает объект `CFont`.

```
CFont();
```

### <a name="remarks"></a>Примечания

Получившийся объект должен быть инициализирован с `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, или `CreatePointFontIndirect` прежде чем можно будет использовать.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

##  <a name="createfont"></a>  CFont::CreateFont

Инициализирует `CFont` объекта с заданными характеристиками.

```
BOOL CreateFont(
    int nHeight,
    int nWidth,
    int nEscapement,
    int nOrientation,
    int nWeight,
    BYTE bItalic,
    BYTE bUnderline,
    BYTE cStrikeOut,
    BYTE nCharSet,
    BYTE nOutPrecision,
    BYTE nClipPrecision,
    BYTE nQuality,
    BYTE nPitchAndFamily,
    LPCTSTR lpszFacename);
```

### <a name="parameters"></a>Параметры

*nHeight*<br/>
Задает требуемую высоту (в логических единицах) шрифта. См. в разделе `lfHeight` членом [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)структуры в пакете SDK для Windows, описание. Абсолютное значение *nHeight* не должна превышать 16 384 единицы устройства после его преобразования. Для всех сравнений высоты средство сопоставления шрифтов ищет наибольший размер шрифта должен превышать запрошенный размер или наименьший размер шрифта Если запрошенный размер превышает всех шрифтов.

*nWidth*<br/>
Указывает среднюю ширину (в логических единицах) символов в шрифте. Если *nWidth* равно 0, соотношение сторон устройства будет сопоставлена с пропорциями доступных шрифтов, чтобы найти наиболее подходящие, который определяется абсолютное значение разницы.

*nEscapement*<br/>
Указывает угол между вектором наклона и осью х поверхность отображения (в единицах 0,1 градусов). Вектором проходит через происхождение первый и последний символы в строке. Угол измеряется против часовой стрелки от оси x. См. в разделе `lfEscapement` члена в `LOGFONT` структуры в пакете SDK для Windows, Дополнительные сведения.

*nOrientation*<br/>
Задает угол (в единицах 0,1 градусов) между базовой линии символа и осью х. Угол измеряется против часовой стрелки от оси x для системы координат, в которых оси y вниз и по часовой стрелке от оси x для системы координат, в которых работает оси y.

*nWeight*<br/>
Задает плотность шрифта (в пикселях замыкающего на 1000). См. в разделе *lfWeight* члена в `LOGFONT` структуры в пакете SDK для Windows, Дополнительные сведения. Описаны значения являются приблизительными; Фактический внешний вид зависит от шрифта. Для некоторых шрифтов существуют только FW_NORMAL FW_REGULAR и FW_BOLD весовые коэффициенты. Если FW_DONTCARE указан, используется вес по умолчанию.

*bItalic*<br/>
Указывает, является ли шрифт курсивом.

*bUnderline*<br/>
Указывает, является ли шрифт подчеркнутым.

*cStrikeOut*<br/>
Указывает, являются ли два прохода символов в шрифте. Указывает зачеркнутый шрифт, если задать ненулевое значение.

*nCharSet*<br/>
Указывает шрифт символа setSee `lfCharSet` члена в `LOGFONT` структуры в пакете Windows SDK для списка значений.

Набор символов OEM зависит от системы.

Шрифты с других наборов символов могут существовать в системе. Приложения, использующего шрифт с набором неизвестный символ не следует пытаться преобразовать или интерпретации строк, которые должны отображаться с помощью данного шрифта. Вместо этого строки должны передаваться напрямую к драйверу устройства вывода.

Средство сопоставления шрифтов не использует значение DEFAULT_CHARSET. Приложение может использовать это значение, чтобы разрешить имя и размер шрифта для полного описания логического шрифта. Если шрифт с заданным именем не существует, можно заменить шрифт из любой набор символов для заданного шрифта. Чтобы избежать непредвиденных результатов, приложения должны использовать значение DEFAULT_CHARSET только в случае необходимости.

*nOutPrecision*<br/>
Указывает точность требуемых выходных данных. Точность определяет, насколько выходные данные должны соответствовать выводимых высота, ширина, ориентация символов, наклон и шаг. См. в разделе `lfOutPrecision` члена в `LOGFONT` структуры в пакете SDK для Windows, список значений и Дополнительные сведения.

*nClipPrecision*<br/>
Указывает точность отсечения нужное. Этот параметр определяет как отсекать символы, которые частично вне области обрезки. См. в разделе `lfClipPrecision` члена в `LOGFONT` структуры в пакете Windows SDK для списка значений.

Чтобы использовать встроенный шрифт только для чтения, приложения необходимо указать CLIP_ENCAPSULATE.

Чтобы обеспечить согласованное поворота устройства, TrueType и векторные шрифты, приложение может использовать оператор OR для объединения значений CLIP_LH_ANGLES с любым из других *nClipPrecision* значения. Если бита CLIP_LH_ANGLES поворота для всех шрифтов зависит от ориентации системы координат для левши и правши. (Дополнительные сведения о ориентацию системы координат, см. в описании элемента *nOrientation* параметр.) Если CLIP_LH_ANGLES не задано, шрифты устройства всегда Повернуть против часовой стрелки, но поворот другие шрифты зависит от ориентации системы координат.

*nQuality*<br/>
Указывает качество шрифта выходных данных, которое определяет, как тщательно GDI необходимо добиваться соответствия параметров логического шрифта те из физического шрифта. См. в разделе `lfQuality` члена в `LOGFONT` структуры в пакете Windows SDK для списка значений.

*nPitchAndFamily*<br/>
Указывает шаг и семейство шрифта. См. в разделе `lfPitchAndFamily` члена в `LOGFONT` структуры в пакете SDK для Windows, список значений и Дополнительные сведения.

*lpszFacename*<br/>
Объект `CString` или указатель на заканчивающуюся нулем строку, которая указывает название гарнитуры шрифта. Длина этой строки не должна превышать 30 символов. Windows [EnumFontFamilies](/windows/desktop/api/wingdi/nf-wingdi-enumfontfamiliesa) функция может использоваться для перечисления всех доступных шрифтов. Если *lpszFacename* имеет значение NULL, GDI использует аппаратно независимые шрифта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Шрифт впоследствии может быть выбран в качестве шрифта для любого контекста устройства.

`CreateFont` Функция не приводит к созданию нового шрифта Windows GDI. Он просто выбирает ближайшее соответствие из физических шрифтов, доступных для GDI.

Приложения могут использовать параметры по умолчанию для большинства параметров при создании логического шрифта. Параметры, которые необходимо обязательно указать конкретные значения являются *nHeight* и *lpszFacename*. Если *nHeight* и *lpszFacename* не заданы, используемые приложением, логического шрифта, который создается зависящие от устройства.

После завершения работы с `CFont` объект, созданный `CreateFont` функции, используйте `CDC::SelectObject` чтобы выбрать другой шрифт в контексте устройства, удалите `CFont` объект, который больше не используется.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect

Инициализирует `CFont` объекта с параметрами, приведенными в [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)структуры.

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>Параметры

*lpLogFont*<br/>
Указывает на `LOGFONT` структура, определяющая характеристики логического шрифта.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Шрифт впоследствии может быть выбран в качестве текущий шрифт для любого устройства.

Он имеет характеристики, указанный в [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) структуры. При выборе шрифта с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функция-член, средство сопоставления шрифтов GDI пытается сопоставить логического шрифта с помощью существующих физических шрифтов. Если средство сопоставления шрифтов не может найти точное совпадение для логического шрифта, он предоставляет альтернативный шрифт, характеристики которых соответствует столько запрошенного характеристики максимально.

Если требуется больше не `CFont` объект, созданный `CreateFontIndirect` функции, используйте `CDC::SelectObject` чтобы выбрать другой шрифт в контексте устройства, удалите `CFont` объект, который больше не используется.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

##  <a name="createpointfont"></a>  CFont::CreatePointFont

Эта функция предоставляет простой способ создать шрифт указанной гарнитуры и размер в пунктах.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Параметры

*nPointSize*<br/>
Требуемая высота шрифта в десятых долях точку. (К примеру, передайте 120, чтобы запросить шрифта 12 пунктов).

*lpszFaceName*<br/>
Объект `CString` или указатель на заканчивающуюся нулем строку, которая указывает название гарнитуры шрифта. Длина этой строки не должна превышать 30 символов. Windows "EnumFontFamilies функция может использоваться для перечисления всех доступных шрифтов. Если *lpszFaceName* имеет значение NULL, GDI использует аппаратно независимые шрифта.

*pDC*<br/>
Указатель на [CDC](../../mfc/reference/cdc-class.md) , который может использоваться для преобразования высоту в *nPointSize* логических единиц. Если значение равно NULL, контекста устройства экран используется для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешно, иначе — 0.

### <a name="remarks"></a>Примечания

Он автоматически преобразует высоту в *nPointSize* для логических устройств с помощью объекта CDC, на которые указывают *pDC*.

После завершения работы с `CFont` объект, созданный `CreatePointFont` функцию, сначала выберите шрифт из контекста устройства, а затем удалить `CFont` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect

Эта функция совпадает со значением [CreateFontIndirect](#createfontindirect) за исключением того, что `lfHeight` членом `LOGFONT` интерпретируется в десятых долях точки, а не устройство единиц.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Параметры

*lpLogFont*<br/>
Указывает на [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) структура, определяющая характеристики логического шрифта. `lfHeight` Членом `LOGFONT` структуры измеряется в десятых долях точку, а не в логических единицах. (Например, задать `lfHeight` 120, чтобы запросить шрифта 12 пунктов.)

*pDC*<br/>
Указатель на [CDC](../../mfc/reference/cdc-class.md) , который может использоваться для преобразования высоту в `lfHeight` логических единиц. Если значение равно NULL, контекста устройства экран используется для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешно, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция автоматически преобразует высоту в `lfHeight` для логических устройств с помощью объекта CDC, на которые указывают *pDC* перед передачей `LOGFONT` структура в Windows.

После завершения работы с `CFont` объект, созданный `CreatePointFontIndirect` функцию, сначала выберите шрифт из контекста устройства, а затем удалить `CFont` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

##  <a name="fromhandle"></a>  CFont::FromHandle

Возвращает указатель на `CFont` объект для заданного дескриптора HFONT на объект шрифта Windows GDI.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>Параметры

*hFont*<br/>
HFONT дескриптор шрифта Windows.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CFont` объекта, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если `CFont` объект еще не присоединен к дескриптору, временный `CFont` созданный и присоединенный объект. Этот временный `CFont` объект является допустимым, только пока очередном приложение время простоя в свой цикл событий, после чего график все временные объекты будут удалены. Другими словами — это временный объект является допустимым только во время обработки сообщения одного окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

##  <a name="getlogfont"></a>  CFont::GetLogFont

Вызывайте эту функцию для извлечения копии `LOGFONT` структуры для `CFont`.

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>Параметры

*pLogFont*<br/>
Указатель на [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) структуры, чтобы получать информацию о шрифте.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполняется успешно, в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

##  <a name="operator_hfont"></a>  HFONT CFont::operator

Этот оператор используется для получения дескриптора Windows GDI шрифта, подключенный к `CFont` объекта.

```
operator HFONT() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор объекта шрифта Windows GDI подключен к `CFont` Если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Так как этот оператор автоматически используется для преобразования из `CFont` для [шрифты и текст](/windows/desktop/gdi/fonts-and-text), вы можете передать `CFont` объектов для функций, которые ожидают HFONTs.

Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](/windows/desktop/gdi/graphic-objects) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
