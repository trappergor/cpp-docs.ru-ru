---
title: Класс CAnimateCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
dev_langs:
- C++
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e52ff062f8ba22eddc7a87e182b267b006f3094
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402412"
---
# <a name="canimatectrl-class"></a>Canimatectrl-класс

Предоставляет функциональные возможности стандартного элемента управления анимациями Windows.

## <a name="syntax"></a>Синтаксис

```
class CAnimateCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Создает объект `CAnimateCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimateCtrl::Close](#close)|Закрывает AVI-файла.|
|[CAnimateCtrl::Create](#create)|Создает элемент управления анимации и присоединяет его к `CAnimateCtrl` объекта.|
|[CAnimateCtrl::CreateEx](#createex)|Создает элемент управления анимации с указанным расширенные стили Windows и присоединяет его к `CAnimateCtrl` объекта.|
|[CAnimateCtrl::IsPlaying](#isplaying)|Указывает, воспроизводится ли с чередованием аудио-видео (AVI)-файла.|
|[CAnimateCtrl::Open](#open)|Открывает AVI-файла из файла или ресурса и отображает первый кадр.|
|[CAnimateCtrl::Play](#play)|Воспроизведение AVI-файла без звука.|
|[CAnimateCtrl::Seek](#seek)|Отображает выбранный одним кадром AVI-файла.|
|[CAnimateCtrl::Stop](#stop)|Останавливает воспроизведение AVI-файла.|

## <a name="remarks"></a>Примечания

Этот элемент управления (и, следовательно `CAnimateCtrl` класс) доступны только для программ, работающих в Windows 95, Windows 98 и Windows NT версии 3.51 и более поздних версиях.

Элемент управления анимации является прямоугольное окно, отображающее клипа в формате AVI (аудио видео с чередованием) — стандартный формат видео и аудио Windows. AVI-файла представляет собой ряд кадры растрового изображения, например фильм.

Элементы управления анимацией можно воспроизведение только простой AVI. В частности клипы, воспроизводимый элементом управления анимации должна соответствовать следующим требованиям:

- Должно быть ровно один поток видео, и он должен иметь по крайней мере одного кадра.

- Может существовать не более двух потоков в файле (обычно поток, при его наличии, является аудиопоток, несмотря на то, что отображается этот элемент управления не обрабатывает аудиоданных).

- Клип должны быть без сжатия или с применением сжатия RLE8.

- Палитра изменения запрещены в поток видео.

AVI-файла можно добавить в приложение как ресурс AVI, или он может сопровождать приложения как отдельный файл AVI.

Поскольку ваш поток продолжает выполнение, пока отображается AVI-файла, часто применяются для элемента управления анимации является указывает действие системы во время длительной операции. Например диалоговое окно поиска проводника отображает скользящего увеличительное стекло как система выполняет поиск файла.

Если вы создаете `CAnimateCtrl` объекта в диалоговое окно, поле или из ресурса диалогового окна, с помощью редактора диалоговых окон, он будет автоматически уничтожен, когда пользователь закрывает диалоговое окно.

Если вы создаете `CAnimateCtrl` объекта в окне, необходимо уничтожить его. Если вы создаете `CAnimateCtrl` объект в стеке, он будет удален автоматически. При создании `CAnimateCtrl` объект в куче с помощью **новый** функцию, необходимо вызвать **удалить** в объекте уничтожить его. Если при создании нового производного класса от `CAnimateCtrl` и выделять память в этом классе, переопределить `CAnimateCtrl` деструктор для удаления из выделений.

Дополнительные сведения об использовании `CAnimateCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CAnimateCtrl](../../mfc/using-canimatectrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="canimatectrl"></a>  CAnimateCtrl::CAnimateCtrl

Создает объект `CAnimateCtrl`.

```
CAnimateCtrl();
```

### <a name="remarks"></a>Примечания

Необходимо вызвать [создать](#create) перед тем как выполнять другие операции в объекте при создании функции-члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

##  <a name="close"></a>  CAnimateCtrl::Close

Закрывает AVI-файла, который ранее был открыт в элементе управления "анимация" (если таковые имеются) и удаляет его из памяти.

```
BOOL Close();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [CAnimateCtrl::CAnimateCtrl](#canimatectrl).

##  <a name="create"></a>  CAnimateCtrl::Create

Создает элемент управления анимации и присоединяет его к `CAnimateCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Задает стиль элемента управления анимации. Применить любое сочетание windows, стили, описанные в разделе «Примечания» и стили элемента управления анимации, описано в разделе [стили элемента управления анимации](/windows/desktop/Controls/animation-control-styles) в пакете Windows SDK.

*Rect*<br/>
Указывает положение и размер элемента управления анимации. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](../../mfc/reference/rect-structure1.md) структуры.

*pParentWnd*<br/>
Указывает родительскому окну элемента управления анимации, обычно `CDialog`. Он не должен иметь значение NULL.

*nID*<br/>
Указывает идентификатор элемента управления анимации.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CAnimateCtrl` в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает отображается этот элемент управления и прикрепляет его к `CAnimateCtrl` объекта.

Примените следующий [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления анимации.

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED редко

Если вы хотите использовать windows расширенных стилей с элементом управления анимации, вызвать [CreateEx](#createex) вместо `Create`.

Помимо стилей окна, перечисленных выше можно применить один или несколько стилей элемента управления анимации в элемент управления анимации. Пакет SDK Windows, Дополнительные сведения см. в разделе на [стили элемента управления анимации](/windows/desktop/Controls/animation-control-styles).

### <a name="example"></a>Пример

  См. в примере [CAnimateCtrl::CAnimateCtrl](#canimatectrl).

##  <a name="createex"></a>  CAnimateCtrl::CreateEx

Создает элемент управления (дочернего окна) и связывает его с `CAnimateCtrl` объекта.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) в пакете Windows SDK.

*dwStyle*<br/>
Задает стиль элемента управления анимации. Применить любое сочетание окна и Стили анимации элемента управления, описанных в [стили элемента управления анимации](/windows/desktop/Controls/animation-control-styles) в пакете Windows SDK.

*Rect*<br/>
Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родительским для элемента управления.

*nID*<br/>
Идентификатор элемента управления дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.

##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying

Указывает, воспроизводится ли с чередованием аудио-видео (AVI)-файла.

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если воспроизводится AVI-файла; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [ACM_ISPLAYING](/windows/desktop/Controls/acm-isplaying) сообщения, который описан в пакете Windows SDK.

##  <a name="open"></a>  CAnimateCtrl::Open

Вызывайте эту функцию, чтобы открыть AVI-файла и отобразить его первый кадр.

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Объект `CString` объект или указатель на заканчивающуюся нулем строку, содержащую либо имя файла AVI или имя ресурса AVI. Если этот параметр имеет значение NULL, система закрывает AVI-файла, который ранее был открыт для анимации элемента управления, если таковые имеются.

*nID*<br/>
Идентификатор ресурса AVI. Если этот параметр имеет значение NULL, система закрывает AVI-файла, который ранее был открыт для анимации элемента управления, если таковые имеются.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

AVI ресурс загружается из модуля, который создал элемент управления анимации.

`Open` не поддерживает звук в AVI-файла; можно открыть только автоматической клипов AVI.

Если для элемента управления анимации `ACS_AUTOPLAY` стиль, отображается этот элемент управления будет автоматически запуск воспроизведения клипа сразу после его открывает его. Она будет продолжать воспроизведения клипа в фоновом режиме, пока поток продолжает выполнение. После завершения клипа воспроизведение, он будет автоматически повторяться.

Если для элемента управления анимации `ACS_CENTER` стиль, AVI-файла будет по центру в элементе управления, и размер элемента управления не изменится. Если отображается этот элемент управления не имеет `ACS_CENTER` стиль, элемент управления будет изменяться при открытии AVI-файла для размера изображений в AVI-файла. Положение верхнего левого угла элемента управления не изменится, только размер элемента управления.

Если для элемента управления анимации `ACS_TRANSPARENT` стиль, будет отображен первый кадр с прозрачным фоном, а не указанный цвет фона в анимации клипа.

### <a name="example"></a>Пример

  См. в примере [CAnimateCtrl::CAnimateCtrl](#canimatectrl).

##  <a name="play"></a>  CAnimateCtrl::Play

Вызывайте эту функцию для воспроизведения AVI-файла в элемент управления анимации.

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>Параметры

*nFrom*<br/>
Отсчитываемый от нуля индекс кадра, где начинается воспроизведение. Значение должно быть меньше 65 536. Значение 0 означает, что будет начинаться с первого кадра в AVI-файла.

*nДля того*<br/>
Отсчитываемый от нуля индекс кадра где воспроизведение завершается. Значение должно быть меньше 65 536. Значение - 1 означает ограничивается последнего кадра в AVI-файла.

*nRep*<br/>
Количество раз, чтобы воспроизвести AVI-файла. Значение - 1 означает неограниченное время воспроизведения файла.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Отображается этот элемент управления будет воспроизводиться клипа в фоновом режиме, пока поток продолжает выполнение. Если для элемента управления анимации `ACS_TRANSPARENT` стиль, AVI-файла будет воспроизводиться с помощью прозрачный фон, а не цвет фона, указанный в анимации клипа.

### <a name="example"></a>Пример

  См. в примере [CAnimateCtrl::CAnimateCtrl](#canimatectrl).

##  <a name="seek"></a>  CAnimateCtrl::Seek

Вызывайте эту функцию для статически отображения одним кадром AVI-файла.

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>Параметры

*nДля того*<br/>
Отсчитываемый от нуля индекс кадра для отображения. Значение должно быть меньше 65 536. Значение 0 означает, что отображения первого кадра в AVI-файла. Значение -1 означает, что отображение последнего кадра в AVI-файла.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Если для элемента управления анимации `ACS_TRANSPARENT` стиль, AVI-файла будет отображен с прозрачным фоном, а не указанный цвет фона в анимации клипа.

### <a name="example"></a>Пример

  См. в примере [CAnimateCtrl::CAnimateCtrl](#canimatectrl).

##  <a name="stop"></a>  CAnimateCtrl::Stop

Вызывайте эту функцию, чтобы остановить воспроизведение AVI-файла в элемент управления анимации.

```
BOOL Stop();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [CAnimateCtrl::CAnimateCtrl](#canimatectrl).

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl::Create](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)

