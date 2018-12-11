---
title: Класс CStatic
ms.date: 11/04/2016
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
ms.openlocfilehash: ab25cad77ee0f11167661bb27b408dd5e92b51f9
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178698"
---
# <a name="cstatic-class"></a>Класс CStatic

Предоставляет функции статического элемента управления Windows.

## <a name="syntax"></a>Синтаксис

```
class CStatic : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStatic::CStatic](#cstatic)|Создает объект `CStatic`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStatic::Create](#create)|Создает статический элемент управления Windows и присоединяет его к `CStatic` объекта.|
|[CStatic::DrawItem](#drawitem)|Переопределение для рисования владельцем статический элемент управления.|
|[CStatic::GetBitmap](#getbitmap)|Извлекает дескриптор растрового изображения, при помощи [SetBitmap](#setbitmap).|
|[CStatic::GetCursor](#getcursor)|Извлекает дескриптор изображения курсора заданные ранее с помощью [SetCursor](#setcursor).|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Извлекает дескриптор расширенного метафайла при помощи [SetEnhMetaFile](#setenhmetafile).|
|[CStatic::GetIcon](#geticon)|Извлекает дескриптор значка, при помощи [SetIcon](#seticon).|
|[CStatic::SetBitmap](#setbitmap)|Указывает растровое изображение для отображения в статического элемента управления.|
|[CStatic::SetCursor](#setcursor)|Задает изображение курсор для отображения в статического элемента управления.|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Указывает расширенный метафайл для отображения в статического элемента управления.|
|[CStatic::SetIcon](#seticon)|Задает значок, отображаемый на статический элемент управления.|

## <a name="remarks"></a>Примечания

Статический элемент управления отображает текстовую строку, поле, прямоугольник, значок, курсор, точечный рисунок или расширенного метафайла. Его можно использовать метки, поле или выделять другие элементы управления. Статический элемент управления обычно не принимает входные данные и предоставляет выходные данные; Тем не менее может уведомить родительского объекта щелчки мыши, если она была создана с помощью стиль SS_NOTIFY.

Создайте статический элемент управления в два этапа. Во-первых, вызовите конструктор для создания `CStatic` объекта, а затем вызовите [создать](#create) функция-член для создания статического элемента управления и присоединить его к `CStatic` объекта.

Если вы создаете `CStatic` объекта в диалоговом окне (с помощью ресурса диалогового окна), `CStatic` объект автоматически уничтожается, когда пользователь закрывает диалоговое окно.

Если вы создаете `CStatic` объекта в окне, также может потребоваться уничтожить его. Объект `CStatic` автоматически уничтожается объект, созданный в стеке в пределах этого периода. При создании `CStatic` объект в куче с помощью **новый** функцию, необходимо вызвать **удалить** в объекте уничтожить его, когда вы закончите с ним.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="create"></a>  CStatic::Create

Создает статический элемент управления Windows и присоединяет его к `CStatic` объекта.

```
virtual BOOL Create(
    LPCTSTR lpszText,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID = 0xffff);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Задает текст, записываемый в элементе управления. Если значение равно NULL, текст не будет отображаться.

*dwStyle*<br/>
Указывает стиль окна статический элемент управления. Применить любое сочетание [стили статический элемент управления](../../mfc/reference/styles-used-by-mfc.md#static-styles) к элементу управления.

*rect*<br/>
Указывает положение и размер статического элемента управления. Может быть либо `RECT` структуры или `CRect` объекта.

*pParentWnd*<br/>
Указывает `CStatic` родительского окна, обычно `CDialog` объекта. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор статический элемент управления элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Создать `CStatic` объекта в два этапа. Во-первых, вызовите конструктор `CStatic`, а затем вызвать `Create`, который создает статический элемент управления Windows и присоединяет его к `CStatic` объекта.

Примените следующий [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) на статический элемент управления:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

Если вы собираетесь отображения растрового изображения, курсор, значка или метафайла в статический элемент управления, нужно будет применить один из следующих [статические стили](../../mfc/reference/styles-used-by-mfc.md#static-styles):

- SS_BITMAP использовать этот стиль для растровых изображений.

- SS_ICON использовать этот стиль для значки и курсоры.

- SS_ENHMETAFILE использовать этот стиль для расширенные метафайлы.

Для курсоров точечные рисунки и значки можно также использовать следующий стиль:

- SS_CENTERIMAGE используйте изображение в статического элемента управления по центру.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>  CStatic::CStatic

Создает объект `CStatic`.

```
CStatic();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>  CStatic::DrawItem

Вызывается платформой для рисования владельцем статический элемент управления.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) структуры. Структура содержит сведения о рисуемого элемента и типа требуется рисование.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для реализации рисования для рисуемого владельцем `CStatic` объект (элемент управления имеет стиль SS_OWNERDRAW).

##  <a name="getbitmap"></a>  CStatic::GetBitmap

Возвращает дескриптор растрового изображения, при помощи [SetBitmap](#setbitmap), то есть связанный с `CStatic`.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор в текущую битовую карту, или значение NULL, если отсутствует растровое изображение не задана.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>  CStatic::GetCursor

Возвращает дескриптор курсора, при помощи [SetCursor](#setcursor), то есть связанный с `CStatic`.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор курсора, или значение NULL, если не задано никакой курсор.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile

Возвращает дескриптор расширенного метафайла, при помощи [SetEnhMetafile](#setenhmetafile), то есть связанный с `CStatic`.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор текущего расширенный метафайл, или значение NULL, если не задана без расширенного метафайла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>  CStatic::GetIcon

Получает дескриптор значка, при помощи [SetIcon](#seticon), то есть связанный с `CStatic`.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор текущего значка, или значение NULL, если значок не задан.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>  CStatic::SetBitmap

Связывает новое растровое изображение с статического элемента управления.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Дескриптор точечного рисунка для отрисовки на статический элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор точечного рисунка, который был ранее связан с статический элемент управления, или значение NULL, если точечный рисунок отсутствует был связан с статического элемента управления.

### <a name="remarks"></a>Примечания

Статический элемент управления автоматически отображаются растрового изображения. По умолчанию он будет отображаться в левом верхнем углу и статический элемент управления будет изменяться размер растрового изображения.

Можно использовать различные окна и стили статический элемент управления, включая следующие:

- SS_BITMAP всегда использовать этот стиль для растровых изображений.

- SS_CENTERIMAGE используйте изображение в статического элемента управления по центру. Если изображение больше, чем статический элемент управления, то он будет обрезан. Если это меньше, чем статический элемент управления, пустое пространство вокруг изображения будут заполнены цвет пикселя в верхнем левом углу точечного рисунка.

- MFC предоставляет класс `CBitmap`, который можно использовать при наличии более с растровым изображением, чем просто вызвать Win32 функционировать `LoadBitmap`. `CBitmap`, который содержит один вид объекта GDI, часто используется вместе с `CStatic`, который является `CWnd` класс, используемый для отображения графического объекта в качестве статического элемента управления.

`CImage` — Это класс, ATL и MFC, который позволяет легко работать с независимыми растровые изображения устройства (DIB). Дополнительные сведения см. в разделе [класс CImage](../../atl-mfc-shared/reference/cimage-class.md).

- Обычно это используется для предоставления `CStatic::SetBitmap` объект GDI, который возвращается HBITMAP оператор `CBitmap` или `CImage` объекта. Код для этого, похожий на следующую строку.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```
В следующем примере создается два `CStatic` объектов в куче. Затем он загружает один с системой растрового изображения с помощью `CBitmap::LoadOEMBitmap` , а другой из файла с помощью `CImage::Load`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>  CStatic::SetCursor

Связывает новый образ курсора с помощью статического элемента управления.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Параметры

*hCursor*<br/>
Дескриптор создаваемого курсора для отрисовки на статический элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор курсора, связанный с статический элемент управления, или значение NULL, если курсор не был связан с статического элемента управления.

### <a name="remarks"></a>Примечания

Курсор автоматически рисуется в статического элемента управления. По умолчанию он будет отображаться в левом верхнем углу и статический элемент управления будет изменяться до размера курсора.

Можно использовать различные окна и стили статический элемент управления, включая следующие:

- SS_ICON всегда использовать этот стиль для значки и курсоры.

- Используйте SS_CENTERIMAGE по центру в статического элемента управления. Если изображение больше, чем статический элемент управления, то он будет обрезан. Если это меньше, чем статический элемент управления, пустое пространство вокруг изображения будет заполняться цвет фона статического элемента управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile

Связывает новый образ расширенного метафайла с статического элемента управления.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>Параметры

*hMetaFile*<br/>
Дескриптор расширенного метафайла для отрисовки на статический элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор расширенного метафайла, связанный с статический элемент управления, или значение NULL, если нет расширенного метафайла был связан с статического элемента управления.

### <a name="remarks"></a>Примечания

Статический элемент управления автоматически отображаются расширенного метафайла. Расширенный метафайл масштабируется до размеров статического элемента управления.

Можно использовать различные окна и стили статический элемент управления, включая следующие:

- SS_ENHMETAFILE использовать этот стиль всегда для расширенные метафайлы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>  CStatic::SetIcon

Связывает новый изображение значка с статического элемента управления.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
Дескриптор значка для отрисовки на статический элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор значка, ранее связанного с статический элемент управления, или значение NULL, если значок не был связан с статического элемента управления.

### <a name="remarks"></a>Примечания

Статический элемент управления автоматически отображаются значок. По умолчанию он будет отображаться в левом верхнем углу и статический элемент управления будет изменяться до размера значка.

Можно использовать различные окна и стили статический элемент управления, включая следующие:

- SS_ICON всегда использовать этот стиль для значки и курсоры.

- Используйте SS_CENTERIMAGE по центру в статического элемента управления. Если изображение больше, чем статический элемент управления, то он будет обрезан. Если это меньше, чем статический элемент управления, пустое пространство вокруг изображения будет заполняться цвет фона статического элемента управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
