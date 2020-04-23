---
title: Класс CBitmapButton
ms.date: 11/04/2016
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
ms.openlocfilehash: df21591dec1da5861125d7e9480fb9345aaad061
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752947"
---
# <a name="cbitmapbutton-class"></a>Класс CBitmapButton

Создает элементы управления "кнопка", на которые вместо текста помещаются растровые изображения.

## <a name="syntax"></a>Синтаксис

```
class CBitmapButton : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Формирует объект `CBitmapButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBitmapКнопка:Автозагрузка](#autoload)|Связывает кнопку в диалоговом поле с `CBitmapButton` объектом класса, загружает битную карту (ы) по имени и размеры кнопки, чтобы соответствовать битной карте.|
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Инициализирует объект, загрузив один или несколько названных ресурсов биткарты из файла ресурсов приложения и прикрепив биткарты к объекту.|
|[CBitmapButton:SizetoContent](#sizetocontent)|Размеры кнопки для размещения bitmap.|

## <a name="remarks"></a>Remarks

`CBitmapButton`объекты содержат до четырех бит-карт, которые содержат изображения для различных состояний кнопка может предположить: вверх (или нормально), вниз (или выбраны), сосредоточены, и отключены. Требуется только первая бит-карта; другие не являются обязательными.

Изображения Bitmap-кнопки включают границу вокруг изображения, а также само изображение. Граница обычно играет определенную роль в отображении состояния кнопки. Например, бит-карта для сфокусированного состояния обычно подобна той, которая для состояния вверх, но с влитом прямоугольником, врисуенным с границы или толстой сплошной линией на границе. Бит-карта для состояния с ограниченными возможностями обычно напоминает карту для состояния вверх, но имеет более низкий контраст (например, приглушенный или серый выбор меню).

Эти bitmaps может быть любого размера, но все они рассматриваются как если бы они были того же размера, как bitmap для состояния вверх.

Различные приложения требуют различных комбинаций изображений bitmap:

|Вверх|Вниз|Focused|Выключено|Приложение|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||Кнопка без WS_TABSTOP стиля|
|×|×|×|×|Кнопка dialog со всеми состояниями|
|×|×|×||Кнопка Dialog со стилем WS_TABSTOP|

При создании управления bitmap-кнопкой установите BS_OWNERDRAW стиль, чтобы указать, что кнопка нарисована владельцем. Это приводит к тому, что Windows отправляет WM_MEASUREITEM и WM_DRAWITEM сообщения для кнопки; фреймворк обрабатывает эти сообщения и управляет появлением кнопки для вас.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Создание управления bitmap-кнопкой в клиентской области окна

1. Создайте от одного до четырех изображений bitmap для кнопки.

1. Постройте объект [CBitmapButton.](#cbitmapbutton)

1. Вызов функции [Создания](../../mfc/reference/cbutton-class.md#create) для создания управления кнопкой `CBitmapButton` Windows и прикрепите его к объекту.

1. Позвоните в функцию участника [LoadBitmaps](#loadbitmaps) для загрузки ресурсов bitmap после построения кнопки bitmap.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Включить управление бит-кнопок в диалоговую будку

1. Создайте от одного до четырех изображений bitmap для кнопки.

1. Создайте шаблон диалога с кнопкой «Нарисовать владельца», расположенную там, где требуется кнопка bitmap. Размер кнопки в шаблоне не имеет значения.

1. Установите подпись кнопки к значению, такому как "MYIMAGE" и определите символ для кнопки, например IDC_MYIMAGE.

1. В скрипте ресурса приложения привайте каждому из изображений, созданных для кнопки, идентификатор, созданный путем податливого одной из букв "U", "D", "F" или "X" (для вверх, вниз, сфокусированный и отключенный) к строке, используемой для подписи к кнопке в шаге 3. Для заголовка кнопки "MYIMAGE", например, идентификации будут "MYIMAGEU", "MYIMAGED", "MYIMAGEF" и "MYIMAGEX". Вы **должны** указать идентификатор ваших битовых карт в двойных кавычках. В противном случае редактор ресурса назначит целый teteger ресурсу и MFC выйдет из строя при загрузке изображения.

1. В диалоговом классе приложения (производные от), `CDialog`добавить `CBitmapButton` объект-член.

1. В `CDialog` режиме [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) объекта позвоните функции `CBitmapButton` [AutoLoad](#autoload) объекта, используя в качестве параметров `CDialog` идентификатор управления кнопкой и **указатель** объекта.

Если вы хотите обрабатывать сообщения уведомлений Windows, такие как BN_CLICKED, отправленные управлением bitmap-кнопкой своему родителю (обычно классу, полученному из), `CDialog`добавьте к `CDialog`полученному объекту вход в карту сообщений и функцию члена-обработчика сообщений для каждого сообщения. Уведомления, отправленные `CBitmapButton` объектом, такие же, как и уведомления, отправленные объектом [CButton.](../../mfc/reference/cbutton-class.md)

Класс [CToolBar](../../mfc/reference/ctoolbar-class.md) использует другой подход к кнопкам bitmap.

Для получения `CBitmapButton`дополнительной информации о, см. [Controls](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="cbitmapbuttonautoload"></a><a name="autoload"></a>CBitmapКнопка:Автозагрузка

Связывает кнопку в диалоговом поле с `CBitmapButton` объектом класса, загружает битную карту (ы) по имени и размеры кнопки, чтобы соответствовать битной карте.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор управления кнопкой.

*pРодитель*<br/>
Указатель на объект, которому принадлежит кнопка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Используйте `AutoLoad` функцию для инициализации кнопки «нарисовать владельца» в диалоговом поле в качестве кнопки bitmap. Инструкции по использованию этой функции `CBitmapButton` находятся в замечаниях для класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

## <a name="cbitmapbuttoncbitmapbutton"></a><a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton

Создает объект `CBitmapButton`.

```
CBitmapButton();
```

### <a name="remarks"></a>Remarks

После создания объекта `CBitmapButton` C', позвоните [CButton::Создать](../../mfc/reference/cbutton-class.md#create) для создания управления `CBitmapButton` кнопкой Windows и прикрепить его к объекту.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

## <a name="cbitmapbuttonloadbitmaps"></a><a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps

Используйте эту функцию, когда требуется загрузить изображения битовой карты, идентифицированные `AutoLoad` по именам ресурсов или идентификационным номерам, или когда вы не можете использовать эту функцию, потому что, например, вы создаете кнопку bitmap, которая не является частью диалогового окна.

```
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,
    LPCTSTR lpszBitmapResourceSel = NULL,
    LPCTSTR lpszBitmapResourceFocus = NULL,
    LPCTSTR lpszBitmapResourceDisabled = NULL);

BOOL LoadBitmaps(
    UINT nIDBitmapResource,
    UINT nIDBitmapResourceSel = 0,
    UINT nIDBitmapResourceFocus = 0,
    UINT nIDBitmapResourceDisabled = 0);
```

### <a name="parameters"></a>Параметры

*lpszBitmapРесурс*<br/>
Указывает на нулевую строку, содержащую имя карты битовой карты для нормального или "вверх" состояния кнопки bitmap. Обязательный элемент.

*lpszBitmapResourceSel*<br/>
Указывает на нулевую строку, содержащую имя битной карты для выбранного или "вниз" состояния кнопки bitmap. Может иметь значение "NULL".

*lpszBitmapResourceFocus*<br/>
Указывает на нулевую строку, содержащую имя битной карты для сфокусированного состояния кнопки bitmap. Может иметь значение "NULL".

*lpszBitmapРесурсов*<br/>
Указывает на нулевую строку, содержащую имя карты битовой карты для состояния отключенной кнопки bitmap. Может иметь значение "NULL".

*nIDBitmapРесурс*<br/>
Указать идентификационный номер ресурса ресурса ресурса bitmap для нормального или "вверх" состояния кнопки bitmap. Обязательный элемент.

*nIDBitmapРесурсСель*<br/>
Указать идентификационный номер ресурса ресурса ресурса bitmap для выбранного или "вниз" состояния кнопки bitmap. Может быть 0.

*nIDBitmapResourceFocus*<br/>
Указать идентификационный номер ресурса ресурса ресурса bitmap для сфокусированного состояния кнопки bitmap. Может быть 0.

*nIDBitmapРесурсовИнвалид*<br/>
Указать идентификационный номер ресурса ресурса ресурса для состояния отключенной кнопки bitmap. Может быть 0.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

## <a name="cbitmapbuttonsizetocontent"></a><a name="sizetocontent"></a>CBitmapButton:SizetoContent

Вызовите эту функцию, чтобы изменить размер кнопки bitmap до размера битовой карты.

```cpp
void SizeToContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
