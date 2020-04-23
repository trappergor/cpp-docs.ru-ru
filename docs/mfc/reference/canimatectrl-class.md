---
title: Класс CAnimateCtrl
ms.date: 11/04/2016
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
ms.openlocfilehash: e570681c899d58e8659635d55da843c23d1e95ee
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752882"
---
# <a name="canimatectrl-class"></a>Класс CAnimateCtrl

Предоставляет функциональные возможности стандартного элемента управления анимациями Windows.

## <a name="syntax"></a>Синтаксис

```
class CAnimateCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Формирует объект `CAnimateCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimateCtrl:Закрыть](#close)|Закрывает клип AVI.|
|[CAnimateCtrl:Создание](#create)|Создает элемент управления анимацией и `CAnimateCtrl` прикрепляет его к объекту.|
|[CAnimateCtrl:CreateEx](#createex)|Создает элемент управления анимацией с указанными расширенными `CAnimateCtrl` стилями Windows и прикрепляет его к объекту.|
|[CAnimateCtrl:Игра](#isplaying)|Указывает, воскоставляется ли аудио-видео interleaved (AVI).|
|[CAnimateCtrl:Открыто](#open)|Открывает клип AVI из файла или ресурса и отображает первый кадр.|
|[CAnimateCtrl::Play](#play)|Воспроизведение клипа AVI без звука.|
|[CAnimateCtrl:Ищите](#seek)|Отображает выбранный один кадр клипа AVI.|
|[CAnimateCtrl:Остановка](#stop)|Прекращает воспроизведение клипа AVI.|

## <a name="remarks"></a>Remarks

Этот элемент управления `CAnimateCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows 95, Windows 98, и Windows NT версии 3.51 и позже.

Управление анимацией представляет собой прямоугольное окно, которое отображает клип в формате AVI (Audio Video Interleaved) — стандартный формат видео/аудио Windows. Клип AVI представляет собой серию кадров bitmap, как и фильм.

Элементы управления анимацией могут воспроизводить только простые клипы AVI. В частности, клипы, воснаряемые элементом управления анимацией, должны соответствовать следующим требованиям:

- Там должно быть точно один поток видео, и он должен иметь по крайней мере один кадр.

- В файле может быть не более двух потоков (обычно другой поток, если он присутствует, представляет собой аудиопоток, хотя управление анимацией игнорирует аудиоинформацию).

- Клип должен быть либо несжатым, либо сжатым с помощью сжатия RLE8.

- В видеопотоке не допускается никаких изменений палитры.

Вы можете добавить клип AVI в ваше приложение в качестве ресурса AVI, или он может сопровождать ваше приложение в качестве отдельного файла AVI.

Поскольку поток продолжает выполнение во время отображения клипа AVI, одно общее использование для управления анимацией — это указание активности системы во время длительной операции. Например, в поле Поиска диалога File Explorer отображается движущееся увеличительное стекло при поиске файла системой.

Если вы `CAnimateCtrl` создаете объект в диалоговом поле или из диалогового ресурса с помощью редактора диалогов, он будет автоматически уничтожен при закрытии диалогового окна.

Если вы `CAnimateCtrl` создаете объект в окне, возможно, потребуется уничтожить его. При создании `CAnimateCtrl` объекта в стеке он уничтожается автоматически. Если вы `CAnimateCtrl` создаете объект на куче с помощью **новой** функции, необходимо **вызвать удалить** объект, чтобы уничтожить его. Если вы получаете `CAnimateCtrl` новый класс и распределяете `CAnimateCtrl` любую память в этом классе, переопределить деструктор, чтобы избавиться от выделений.

Для получения дополнительной `CAnimateCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CAnimateCtrl](../../mfc/using-canimatectrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="canimatectrlcanimatectrl"></a><a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl

Формирует объект `CAnimateCtrl`.

```
CAnimateCtrl();
```

### <a name="remarks"></a>Remarks

Вы должны вызвать функцию члена [Create,](#create) прежде чем вы сможете выполнить любые другие операции на объекте, который вы создаете.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

## <a name="canimatectrlclose"></a><a name="close"></a>CAnimateCtrl:Закрыть

Закрывает клип AVI, который ранее был открыт в управлении анимацией (если таковые имеется) и удаляет его из памяти.

```
BOOL Close();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [для CAnimateCtrl::CAnimateCtrl](#canimatectrl).

## <a name="canimatectrlcreate"></a><a name="create"></a>CAnimateCtrl:Создание

Создает элемент управления анимацией и `CAnimateCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления анимацией. Примените любую комбинацию стилей windows, описанных в разделе Замечания ниже, и стили управления анимацией, описанные в [стилях управления анимацией](/windows/win32/Controls/animation-control-styles) в Windows SDK.

*rect*<br/>
Определяет положение и размер управления анимацией. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT.](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Определяет родительское окно управления анимацией, обычно `CDialog`. Она не должна быть NULL.

*nID*<br/>
Определяет идентификатор управления анимацией.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Вы строите `CAnimateCtrl` в два этапа. Сначала позвоните в конструктор, `Create`а затем вызов, который создает управление `CAnimateCtrl` анимацией и прикрепляет его к объекту.

Примените следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к управлению анимацией.

- WS_CHILD всегда

- WS_VISIBLE обычно

- WS_DISABLED Редко

Если вы хотите использовать расширенные стили окон с `Create`помощью управления анимацией, позвоните [CreateEx](#createex) вместо .

В дополнение к стилям окон, перечисленным выше, вы можете применить один или несколько стилей управления анимацией к управлению анимацией. Дополнительную информацию о [стилях управления анимацией](/windows/win32/Controls/animation-control-styles)можно узнать в SDK Windows.

### <a name="example"></a>Пример

  Смотрите пример [для CAnimateCtrl::CAnimateCtrl](#canimatectrl).

## <a name="canimatectrlcreateex"></a><a name="createex"></a>CAnimateCtrl:CreateEx

Создает элемент управления (детское окно) и `CAnimateCtrl` связывает его с объектом.

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
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Определяет стиль управления анимацией. Применяйте любую комбинацию стилей управления окнами и анимацией, описанные в [стилях управления анимацией](/windows/win32/Controls/animation-control-styles) в Windows SDK.

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Используйте `CreateEx` вместо [создания](#create) для применения расширенных стилей Windows, указанных в предисловии расширенного стиля Windows **WS_EX_.**

## <a name="canimatectrlisplaying"></a><a name="isplaying"></a>CAnimateCtrl:Игра

Указывает, воскоставляется ли аудио-видео interleaved (AVI).

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если клип AVI играет; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Этот метод отправляет [ACM_ISPLAYING](/windows/win32/Controls/acm-isplaying) сообщение, которое описано в SDK Windows.

## <a name="canimatectrlopen"></a><a name="open"></a>CAnimateCtrl:Открыто

Вызовите эту функцию, чтобы открыть клип AVI и отобразить его первый кадр.

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Объект `CString` или указатель на нулевую строку, содержащую либо имя файла AVI, либо имя ресурса AVI. Если этот параметр NULL, система закрывает клип AVI, который был ранее открыт для управления анимацией, если такового.

*nID*<br/>
Идентификатор ресурса AVI. Если этот параметр NULL, система закрывает клип AVI, который был ранее открыт для управления анимацией, если такового.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Ресурс AVI загружается из модуля, создавого управления анимацией.

`Open`не поддерживает звук в клипе AVI; Вы можете открыть только молчание AVI клипы.

Если элемент управления `ACS_AUTOPLAY` анимацией имеет стиль, управление анимацией автоматически начнет воспроизвольно играть клип сразу после его открытия. Он будет продолжать воспроизводить клип в фоновом режиме, пока поток продолжает выполнять. Когда клип будет выполнен воспроизволит, он будет автоматически повторен.

Если элемент управления `ACS_CENTER` анимацией имеет стиль, клип AVI будет сосредоточен в элементе управления, и размер элемента управления не изменится. Если элемент управления анимацией `ACS_CENTER` не имеет стиля, элемент управления будет уменьшен, когда клип AVI будет открыт для размера изображений в клипе AVI. Положение верхнего левого угла управления не изменится, только размер элемента управления.

Если элемент управления `ACS_TRANSPARENT` анимацией имеет стиль, первый кадр будет нарисован с помощью прозрачного фона, а не цвета фона, указанного в анимационном клипе.

### <a name="example"></a>Пример

  Смотрите пример [для CAnimateCtrl::CAnimateCtrl](#canimatectrl).

## <a name="canimatectrlplay"></a><a name="play"></a>CAnimateCtrl::Play

Вызовите эту функцию, чтобы воспроизвести клип AVI в управлении анимацией.

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>Параметры

*nОт*<br/>
Нулевой индекс кадра, где начинается игра. Значение должно быть меньше 65 536. Значение 0 означает начало с первого кадра в клипе AVI.

*Nto*<br/>
Нулевой индекс кадра, где заканчивается игра. Значение должно быть меньше 65 536. Значение - 1 означает конец с последним кадром в клипе AVI.

*nRep*<br/>
Количество раз, чтобы воспроизвести клип AVI. Значение - 1 означает воспроизведение файла на неопределенный срок.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Управление анимацией будет воспроизводить клип в фоновом режиме, пока поток продолжает исполнять. Если элемент управления `ACS_TRANSPARENT` анимацией имеет стиль, клип AVI будет воспроизводиться с помощью прозрачного фона, а не цвета фона, указанного в анимационном клипе.

### <a name="example"></a>Пример

  Смотрите пример [для CAnimateCtrl::CAnimateCtrl](#canimatectrl).

## <a name="canimatectrlseek"></a><a name="seek"></a>CAnimateCtrl:Ищите

Вызовите эту функцию, чтобы статически отобразить один кадр клипа AVI.

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>Параметры

*Nto*<br/>
Нулевой индекс кадра для отображения. Значение должно быть меньше 65 536. Значение 0 означает отображение первого кадра в клипе AVI. Значение -1 означает отображение последнего кадра в клипе AVI.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Если элемент управления `ACS_TRANSPARENT` анимацией имеет стиль, клип AVI будет нарисован с помощью прозрачного фона, а не цвета фона, указанного в анимационном клипе.

### <a name="example"></a>Пример

Смотрите пример [для CAnimateCtrl::CAnimateCtrl](#canimatectrl).

## <a name="canimatectrlstop"></a><a name="stop"></a>CAnimateCtrl:Остановка

Вызовите эту функцию, чтобы прекратить воспроизведение клипа AVI в управлении анимацией.

```
BOOL Stop();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [для CAnimateCtrl::CAnimateCtrl](#canimatectrl).

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl:Создание](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)
