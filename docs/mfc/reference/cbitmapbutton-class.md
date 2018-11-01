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
ms.openlocfilehash: 6bff87cd7648e1e5f4e0391a0a7fc1a1455a51f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599658"
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
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Создает объект `CBitmapButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBitmapButton::AutoLoad](#autoload)|Связывает кнопку в диалоговом окне с объектом класса `CBitmapButton` классом, загружает bitmap(s) по имени и изменяет размер кнопки в соответствии с растрового изображения.|
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Инициализирует объект путем загрузки один или несколько ресурсов именованный растрового изображения из файла ресурсов приложения и присоединение точечные рисунки в объект.|
|[CBitmapButton::SizeToContent](#sizetocontent)|Размеры кнопки, чтобы вместить растрового изображения.|

## <a name="remarks"></a>Примечания

`CBitmapButton` объекты содержат до четырех точечных рисунков, которые содержат изображения для различных состояний кнопки можно предположить, что: вверх (или обычный), вниз (или только выделенных), с фокусом ввода, а также отключены. Только первый растровое изображение не требуется; остальные записи являются необязательными.

Кнопка с рисунком образы содержат границы вокруг изображения, а также само изображение. Границы обычно играет роль при отображении состояние кнопки. Например растровое изображение для конкретное состояние обычно является наподобие того для ненажатом состоянии, но с пунктирным прямоугольником отступ от границы "или" толстая сплошная линия у границы. Растровое изображение для отключенного состояния обычно напоминает тот, для ненажатом состоянии, но имеет менее контрастных (например, Выбор меню серым цветом или затененный).

Эти точечные рисунки могут быть любого размера, но все рассматриваются, как если бы они были совпадает с размером растрового изображения для ненажатом состоянии.

Различные приложениям требуются различные сочетания растровых изображений:

|Вверх|Вниз|Focused|Отключено|Приложение|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||Кнопка без WS_TABSTOP стиля|
|×|×|×|×|Кнопка диалогового окна с все состояния|
|×|×|×||Диалоговое окно кнопку со стилем WS_TABSTOP|

При создании точечного рисунка кнопки установите стиль BS_OWNERDRAW, чтобы указать, что данная кнопка является владельцем. Это приводит к Windows для отправки сообщений WM_MEASUREITEM и WM_DRAWITEM для кнопки; Платформа обрабатывает эти сообщения и управляет внешний вид кнопки для вас.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Создание растрового изображения кнопки элемента управления в клиентской области окна

1. Создание от одной до четырех точечных рисунков для кнопки.

1. Создать [CBitmapButton](#cbitmapbutton) объекта.

1. Вызовите [создать](../../mfc/reference/cbutton-class.md#create) функцию, чтобы создать элемент управления button в Windows и присоединить его к `CBitmapButton` объекта.

1. Вызовите [LoadBitmaps](#loadbitmaps) функция-член для загрузки ресурсов растрового изображения, после создания кнопка с рисунком.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Чтобы включить элемент управления button точечного рисунка в диалоговом окне

1. Создание от одной до четырех точечных рисунков для кнопки.

1. Создание шаблона диалогового окна с помощью кнопки рисуемый владельцем, расположенный место кнопка с рисунком. Размер кнопки в шаблоне не имеет значения.

1. Присвоено значение, например «MYIMAGE» название кнопки и символ для кнопок, такие как IDC_MYIMAGE.

1. В сценарий ресурсов приложения Предоставьте каждой из образов, созданных для кнопки сформировать, добавив одну из букв «U», «D», «F», идентификатор, или «X» (для вверх, вниз, с фокусом ввода и отключен) строка, используемая для подписи кнопки в шаге 3. Для подписи кнопки «MYIMAGE», например, идентификаторы будет «MYIMAGEU», «MYIMAGED», «MYIMAGEF» и «MYIMAGEX.» Вы **необходимо** укажите идентификатор точечных рисунков, заключенные в двойные кавычки. В противном случае редактор ресурсов назначит целое число к ресурсу и MFC завершится ошибкой при загрузке образа.

1. В класс диалогового окна приложения (производный от `CDialog`), добавьте `CBitmapButton` объект-член.

1. В `CDialog` объекта [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) подпрограмм, вызов `CBitmapButton` объекта [автозагрузки](#autoload) функции используются в качестве параметров идентификатор элемента управления кнопки и `CDialog` объекта **это** указатель.

Если вы хотите обрабатывать сообщения уведомлений Windows, например BN_CLICKED, посылается элементом управления кнопка с рисунком с родительским (обычно класс, производный от `CDialog`), добавьте `CDialog`-производный объект члена запись и обработчик сообщений схемы сообщений функция для каждого сообщения. Уведомления, отправленные `CBitmapButton` имеют такие же, как отправленные [CButton](../../mfc/reference/cbutton-class.md) объекта.

Класс [CToolBar](../../mfc/reference/ctoolbar-class.md) использует другой подход к кнопками с точечными рисунками.

Дополнительные сведения о `CBitmapButton`, см. в разделе [элементов управления](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

##  <a name="autoload"></a>  CBitmapButton::AutoLoad

Связывает кнопку в диалоговом окне с объектом класса `CBitmapButton` классом, загружает bitmap(s) по имени и изменяет размер кнопки в соответствии с растрового изображения.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления кнопки.

*pParent*<br/>
Указатель на объект, которому принадлежит кнопки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `AutoLoad` функцию для инициализации кнопка пользовательской отрисовки в диалоговом окне как кнопка растрового изображения. Инструкции по использованию этой функции находятся в разделе «Примечания» для `CBitmapButton` класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton

Создает объект `CBitmapButton`.

```
CBitmapButton();
```

### <a name="remarks"></a>Примечания

После создания C++ `CBitmapButton` , вызовите [CButton::Create](../../mfc/reference/cbutton-class.md#create) для создания элемента управления button Windows и присоединить его к `CBitmapButton` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps

Используйте эту функцию, если вы хотите загрузить точечных рисунков, определенной их идентификаторы или имена ресурсов, или когда невозможно использовать `AutoLoad` работать так, как, например, вы создаете кнопку растрового изображения, которая не входит в диалоговом окне.

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

*lpszBitmapResource*<br/>
Указатель на заканчивающуюся нулем строку, содержащая имя точечного рисунка для растрового изображения кнопки normal или состояние «вверх». Обязательно.

*lpszBitmapResourceSel*<br/>
Указывает, заканчивающуюся нулем строку, содержащая имя точечного рисунка, для выбранного кнопка с рисунком или состояние «вниз». Может иметь значение NULL.

*lpszBitmapResourceFocus*<br/>
Состояние указывает на заканчивающуюся нулем строку, содержащую имя растрового изображения для кнопки точечного рисунка с фокусом ввода. Может иметь значение NULL.

*lpszBitmapResourceDisabled*<br/>
Указатель на заканчивающуюся нулем строку, содержащая имя точечного рисунка для кнопки растрового изображения при отключенном состоянии. Может иметь значение NULL.

*nIDBitmapResource*<br/>
Указывает идентификатор ресурса точечного рисунка для кнопки точечного рисунка normal или «up» состояние ресурсов. Обязательно.

*nIDBitmapResourceSel*<br/>
Указывает идентификатор ресурса точечного рисунка ресурса для выбранного кнопка с рисунком или состояние «вниз». Может быть равно 0.

*nIDBitmapResourceFocus*<br/>
Указывает идентификатор ресурса точечного рисунка для растрового изображения кнопки конкретное состояние ресурсов. Может быть равно 0.

*nIDBitmapResourceDisabled*<br/>
Число ресурсов идентификатор ресурса точечного рисунка для кнопки растрового изображения при отключенном состоянии. Может быть равно 0.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent

Вызывайте эту функцию, чтобы изменить размер кнопки растрового изображения до размера точечного рисунка.

```
void SizeToContent();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC CTRLTEST](../../visual-cpp-samples.md)<br/>
[Класс CButton](../../mfc/reference/cbutton-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

