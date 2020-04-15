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
ms.openlocfilehash: e5c3705c0aa2fd90e73cb54ba5a97c252ed2cf83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371646"
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
|[Статический::Статический](#cstatic)|Формирует объект `CStatic`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStatic::Создание](#create)|Создает статический элемент управления Windows `CStatic` и прикрепляет его к объекту.|
|[CStatic::DrawItem](#drawitem)|Переопределение, чтобы нарисовать нарисованный владельцем статический элемент управления.|
|[Статичный:GetBitmap](#getbitmap)|Извлекает ручку бит-карты, ранее установленной [setBitmap.](#setbitmap)|
|[Штаб-класс:Геткурсор](#getcursor)|Извлекает ручку изображения курсора, ранее установленного set with [SetCursor.](#setcursor)|
|[Штаб-нибудь:GetEnhMetaFile](#getenhmetafile)|Извлекает ручку расширенного метафайла, ранее установленного set with [SetEnhMetaFile.](#setenhmetafile)|
|[Статичный::GetIcon](#geticon)|Извлекает ручку значка, ранее установленную [SetIcon.](#seticon)|
|[Статический::SetBitmap](#setbitmap)|Определяет битную карту для отображения в статическом элементе управления.|
|[Штаб-класс:SetCursor](#setcursor)|Определяет изображение курсора для отображения в статическом элементе управления.|
|[Штаб-телефон:SetEnhMetaFile](#setenhmetafile)|Определяет расширенный метафайл, который будет отображаться в статическом элементе управления.|
|[CStatic::SetIcon](#seticon)|Определяет значок для отображения в элементном элементе управления.|

## <a name="remarks"></a>Remarks

Статический элемент управления отображает текстовую строку, коробку, прямоугольник, значок, курсор, бит-карту или расширенный метафил. Он может быть использован для маркировки, коробки или отдельных других элементов управления. Статический элемент управления обычно не принимает входных данных и не обеспечивает вывода; однако, он может уведомить своего родителя щелчков мыши, если он создан с SS_NOTIFY стилем.

Создайте статический элемент управления в два этапа. Сначала позвоните в конструктор, `CStatic` чтобы построить объект, затем позвоните в функцию `CStatic` члена [Create,](#create) чтобы создать статический элемент управления и прикрепить его к объекту.

При создании `CStatic` объекта в диалоговом поле (через ресурс `CStatic` диалога) объект автоматически уничтожается при закрытии диалогового окна.

Если вы `CStatic` создаете объект в окне, возможно, вам также придется уничтожить его. Объект, `CStatic` созданный на стеке в окне, автоматически уничтожается. Если вы `CStatic` создаете объект на куче с помощью **новой** функции, необходимо **вызвать удалить** объект, чтобы уничтожить его, когда вы закончите с ним.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cstaticcreate"></a><a name="create"></a>CStatic::Создание

Создает статический элемент управления Windows `CStatic` и прикрепляет его к объекту.

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
Определяет текст для размещения в элементе управления. Если NULL, текст не будет виден.

*dwStyle*<br/>
Определяет стиль окна элементаражаемого элемента управления. Примените к управлению любую комбинацию [статических стилей управления.](../../mfc/reference/styles-used-by-mfc.md#static-styles)

*rect*<br/>
Определяет положение и размер статического элемента управления. Это может быть `RECT` либо `CRect` структура, либо объект.

*pParentWnd*<br/>
Определяет родительское `CStatic` окно, обычно `CDialog` объект. Она не должна быть NULL.

*nID*<br/>
Определяет идентификатор управления статического элемента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Постройте `CStatic` объект в два этапа. Сначала позвоните в `CStatic`конструктор, `Create`а затем вызов , который создает статический элемент управления Windows и прикрепляет его к объекту. `CStatic`

Примените следующие [стили окон](../../mfc/reference/styles-used-by-mfc.md#window-styles) к статическому управлению:

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

Если вы собираетесь отображать бит-карту, курсор, значок или метафайл в статическом элементе управления, вам нужно применить один из следующих [статических стилей:](../../mfc/reference/styles-used-by-mfc.md#static-styles)

- SS_BITMAP используйте этот стиль для бит-карт.

- SS_ICON используйте этот стиль для курсоров и иконок.

- SS_ENHMETAFILE Используйте этот стиль для улучшенных метафайлов.

Для курсоров, бит-карт или иконок вы также можете использовать следующий стиль:

- SS_CENTERIMAGE использовать для центриста изображения в статическом элементе управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

## <a name="cstaticcstatic"></a><a name="cstatic"></a>Статический::Статический

Формирует объект `CStatic`.

```
CStatic();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

## <a name="cstaticdrawitem"></a><a name="drawitem"></a>CStatic::DrawItem

Вызывается фреймворком, чтобы нарисовать нарисованный владельцем статический элемент управления.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на структуру [DRAWITEMSTRUCT.](/windows/win32/api/winuser/ns-winuser-drawitemstruct) Структура содержит информацию о элементе, который будет нарисован, и типе требуемого чертежа.

### <a name="remarks"></a>Remarks

Переопределить эту функцию для реализации `CStatic` чертежа для нарисованного владельцем объекта (элемент управления имеет стиль SS_OWNERDRAW).

## <a name="cstaticgetbitmap"></a><a name="getbitmap"></a>Статичный:GetBitmap

Получает ручку бит-карты, ранее установленной с [SetBitmap](#setbitmap), что связано с `CStatic`.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к текущей битной карте, или NULL, если биткарта не была установлена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticgetcursor"></a><a name="getcursor"></a>Штаб-класс:Геткурсор

Получает ручку курсора, ранее установленную с [SetCursor](#setcursor), которая связана с `CStatic`.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к текущему курсору, или NULL, если курсор не был установлен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticgetenhmetafile"></a><a name="getenhmetafile"></a>Штаб-нибудь:GetEnhMetaFile

Получает ручку расширенного метафайла, ранее установленного с [SetEnhMetafile](#setenhmetafile), что связано с `CStatic`.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к текущему расширенному метафайлу, или NULL, если не установлен расширенный метафайл.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticgeticon"></a><a name="geticon"></a>Статичный::GetIcon

Получает ручку значка, ранее установленного с [SetIcon](#seticon), что связано с `CStatic`.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к текущему значку, или NULL, если значок не был установлен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="cstaticsetbitmap"></a><a name="setbitmap"></a>Статический::SetBitmap

Ассоциирует новую бит-карту со статическим управлением.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Ручка битной карты, которая будет нарисована в статическом элементе управления.

### <a name="return-value"></a>Возвращаемое значение

Ручка битной карты, которая ранее была связана со статическим управлением, или NULL, если нет битовой карты, была связана со статическим управлением.

### <a name="remarks"></a>Remarks

Бит-карта будет автоматически нарисована в статическом элементе управления. По умолчанию он будет нарисован в левом верхнем углу, а статический элемент управления будет уменьшен до размера битовой карты.

Вы можете использовать различные стили управления окнами и статические, включая следующие:

- SS_BITMAP Используйте этот стиль всегда для bitmaps.

- SS_CENTERIMAGE использовать для центриста изображения в статическом элементе управления. Если изображение больше статического элемента управления, оно будет обрезано. Если он меньше статического элемента управления, пустое пространство вокруг изображения будет заполнено цветом пикселя в верхнем левом углу битной карты.

- MFC предоставляет `CBitmap`класс, который вы можете использовать, когда вам нужно сделать больше с `LoadBitmap`изображением bitmap, чем просто вызов функции Win32. `CBitmap`, который содержит один вид объекта GDI, `CStatic`часто используется `CWnd` в сотрудничестве с, который является классом, который используется для отображения графического объекта в качестве статического элемента управления.

`CImage`является классом ATL/MFC, который позволяет вам легче работать с независимыми bitmaps устройства (DIB). Для получения дополнительной [CImage Class](../../atl-mfc-shared/reference/cimage-class.md)информации см.

- Типичное использование `CStatic::SetBitmap` заключается в предоставлении объекта GDI, который `CBitmap` `CImage` возвращается оператором HBITMAP или объекта. Код для этого напоминает следующую строку.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```

Следующий пример `CStatic` создает два объекта на куче. Затем он загружает один `CBitmap::LoadOEMBitmap` с помощью системы `CImage::Load`bitmap и другой из файла с помощью.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticsetcursor"></a><a name="setcursor"></a>Штаб-класс:SetCursor

Связывает новое изображение курсора со статическим управлением.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Параметры

*hCursor*<br/>
Ручка курсора, которая будет нарисована в статическом управлении.

### <a name="return-value"></a>Возвращаемое значение

Ручка курсора, ранее связанная со статическим управлением, или NULL, если курсор не был связан со статическим управлением.

### <a name="remarks"></a>Remarks

Курсор будет автоматически нарисован в статическом элементе управления. По умолчанию он будет нарисован в левом верхнем углу, а статический элемент управления будет уменьшен до размера курсора.

Вы можете использовать различные стили управления окнами и статические, включая следующие:

- SS_ICON используйте этот стиль всегда для курсоров и иконок.

- SS_CENTERIMAGE использовать для центра в статический элемент управления. Если изображение больше статического элемента управления, оно будет обрезано. Если он меньше статического элемента управления, пустое пространство вокруг изображения будет заполнено фоновым цветом статического элемента управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticsetenhmetafile"></a><a name="setenhmetafile"></a>Штаб-телефон:SetEnhMetaFile

Ассоциирует новое улучшенное изображение метафайла со статическим управлением.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>Параметры

*hMetaFile*<br/>
Ручка расширенного метафайла, который будет нарисован в статическом элементе управления.

### <a name="return-value"></a>Возвращаемое значение

Ручка расширенного метафайла, ранее связанная со статическим управлением, или NULL, если не было связано с статической обработкой увеличенного метафайла.

### <a name="remarks"></a>Remarks

Улучшенный метафайл будет автоматически нарисован в статическом элементе управления. Улучшенный метафилен масштабируется в соответствии с размером статического элемента управления.

Вы можете использовать различные стили управления окнами и статические, включая следующие:

- SS_ENHMETAFILE Используйте этот стиль всегда для расширения метафайлов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticseticon"></a><a name="seticon"></a>CStatic::SetIcon

Связывает новое изображение значка со статическим управлением.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
Ручка значка, которая будет нарисована в статическом элементе управления.

### <a name="return-value"></a>Возвращаемое значение

Ручка значка, ранее связанная со статическим управлением, или NULL, если значок не был связан со статическим управлением.

### <a name="remarks"></a>Remarks

Значок будет автоматически нарисован в статическом элементе управления. По умолчанию он будет нарисован в левом верхнем углу, а статический элемент управления будет уменьшен до размера значка.

Вы можете использовать различные стили управления окнами и статические, включая следующие:

- SS_ICON используйте этот стиль всегда для курсоров и иконок.

- SS_CENTERIMAGE использовать для центра в статический элемент управления. Если изображение больше статического элемента управления, оно будет обрезано. Если он меньше статического элемента управления, пустое пространство вокруг изображения будет заполнено фоновым цветом статического элемента управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Класс CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
