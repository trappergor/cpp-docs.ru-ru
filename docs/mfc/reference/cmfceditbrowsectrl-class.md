---
title: Класс CMFCEditBrowseCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
ms.openlocfilehash: 31fadc0a960ddfcf216951e1af481983b122ea0f
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821312"
---
# <a name="cmfceditbrowsectrl-class"></a>Класс CMFCEditBrowseCtrl

`CMFCEditBrowseCtrl` Класс поддерживает элемент управления "Обзор", который является редактируемым текстовым полем, которое дополнительно содержит кнопку "Обзор". Когда пользователь нажимает кнопку обзора, элемент управления выполняет настраиваемое действие или отображает стандартное диалоговое окно, содержащее браузер файла или папки в браузере.

## <a name="syntax"></a>Синтаксис

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Конструктор по умолчанию.|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCEditBrowseCtrl:: Енаблебровсебуттон](#enablebrowsebutton)|Включает или выключает (скрывает) кнопку "Обзор".|
|[CMFCEditBrowseCtrl:: Енаблефилебровсебуттон](#enablefilebrowsebutton)|Включает кнопку «Обзор» и помещает элемент управления «Обзор» в режим « *Обзор файлов* ».|
|[CMFCEditBrowseCtrl:: Енаблефолдербровсебуттон](#enablefolderbrowsebutton)|Включает кнопку обзора и размещает элемент управления "Обзор" в режиме *просмотра папок* .|
|[CMFCEditBrowseCtrl:: Мода](#getmode)|Возвращает текущий режим просмотра.|
|[CMFCEditBrowseCtrl:: Онафтерупдате](#onafterupdate)|Вызывается структурой после обновления элемента управления "Обзор" с результатом действия "Обзор".|
|[CMFCEditBrowseCtrl:: OnBrowse](#onbrowse)|Вызывается структурой после нажатия пользователем кнопки "Обзор".|
|[CMFCEditBrowseCtrl:: Ончанжелайаут](#onchangelayout)|Перерисовывает текущий элемент управления "Обзор" для редактирования.|
|[CMFCEditBrowseCtrl:: Ондравбровсебуттон](#ondrawbrowsebutton)|Вызывается платформой для рисования кнопки обзора.|
|[CMFCEditBrowseCtrl:: Ониллегалфиленаме](#onillegalfilename)|Вызвано структурой, когда в элементе управления "поле ввода" было указано недопустимое имя файла.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Преобразует сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) . Синтаксис и дополнительные сведения см. в разделе [CWnd::P ретранслатемессаже](../../mfc/reference/cwnd-class.md#pretranslatemessage).|
|[CMFCEditBrowseCtrl:: Сетбровсебуттонимаже](#setbrowsebuttonimage)|Задает пользовательский образ для кнопки обзора.|

## <a name="remarks"></a>Примечания

Используйте элемент управления "Обзор" для выбора имени файла или папки. При необходимости используйте элемент управления для выполнения настраиваемого действия, например для вывода диалогового окна. Можно отобразить или не отображать кнопку Обзор, а также применить пользовательскую метку или изображение на кнопке.

*Режим просмотра* элемента управления "Обзор" определяет, отображается ли кнопка "Обзор" и какое действие происходит при нажатии кнопки. Дополнительные сведения см. в разделе метод метода [мода](#getmode) .

`CMFCEditBrowseCtrl` Класс поддерживает следующие режимы.

- **Пользовательский режим**

   Настраиваемое действие выполняется при нажатии пользователем кнопки обзора. Например, можно отобразить диалоговое окно, зависящее от приложения.

- **файловый режим**

   Когда пользователь нажимает кнопку "Обзор", отображается стандартное диалоговое окно выбора файла.

- **режим папки**

   Когда пользователь нажимает кнопку "Обзор", отображается стандартное диалоговое окно выбора папки.

## <a name="how-to-specify-an-edit-browse-control"></a>Руководство. Указание элемента управления для изменения обзора

Чтобы включить в приложение элемент управления "Обзор", выполните следующие действия.

1. Если требуется реализовать пользовательский режим просмотра, создайте класс, производный от `CMFCEditBrowseCtrl` класса, а затем переопределите метод [CMFCEditBrowseCtrl:: OnBrowse](#onbrowse) . В переопределенном методе выполните пользовательское действие обзора и обновите элемент управления "Обзор" с результатами.

1. `CMFCEditBrowseCtrl` Внедрите объект или производный объект элемента управления "поле обзора" в родительский объект окна.

1. Если для создания диалогового окна используется **мастер классов** , добавьте элемент управления Edit ( `CEdit`) в форму диалогового окна. Кроме того, добавьте переменную для доступа к элементу управления в файле заголовка. В файле заголовка измените тип переменной с `CEdit` на. `CMFCEditBrowseCtrl` Элемент управления "Обзор" будет создан автоматически. Если **мастер классов**не используется, добавьте `CMFCEditBrowseCtrl` переменную в файл заголовка, а затем вызовите его `Create` метод.

1. При добавлении элемента управления "изменить Просмотр" в диалоговое окно используйте средство **ClassWizard** для настройки обмена данными.

1. Вызовите метод [енаблефолдербровсебуттон](#enablefolderbrowsebutton), [енаблефилебровсебуттон](#enablefilebrowsebutton)или [енаблебровсебуттон](#enablebrowsebutton) , чтобы задать режим просмотра и отобразить кнопку обзора. Вызовите метод метода [мода](#getmode) , чтобы получить текущий режим просмотра.

1. Чтобы предоставить пользовательский образ для кнопки обзора, вызовите метод [сетбровсебуттонимаже](#setbrowsebuttonimage) или переопределите метод [ондравбровсебуттон](#ondrawbrowsebutton) .

1. Чтобы удалить кнопку обзора из элемента управления просмотром, вызовите метод [енаблебровсебуттон](#enablebrowsebutton) с параметром *бенабле* , для которого установлено значение false.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как использовать два метода в `CMFCEditBrowseCtrl` классе: `EnableFolderBrowseButton` и `EnableFileBrowseButton`. Этот пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** афкседитбровсектрл. h

##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl:: Енаблебровсебуттон

Отображает или не отображает кнопку обзора в текущем элементе управления "Обзор".

```
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Значение TRUE для вывода кнопки обзора; Значение FALSE, чтобы не отображать кнопку Обзор. Значение по умолчанию — TRUE.

*сзлабел*<br/>
Метка, отображаемая на кнопке обзора. Значение по умолчанию — " **...** ".

### <a name="remarks"></a>Примечания

Если параметр *бенабле* имеет значение true, реализуйте настраиваемое действие, выполняемое при нажатии кнопки обзора. Чтобы реализовать пользовательское действие, создайте класс, производный от `CMFCEditBrowseCtrl` класса, а затем переопределите его метод [OnBrowse](#onbrowse).

Если параметр *бенабле* имеет значение true, режим просмотра элемента управления равен `BrowseMode_Default`; в противном случае — `BrowseMode_None`значение. Дополнительные сведения о режимах просмотра см. в разделе метод метода [мода](#getmode) .

##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl:: Енаблефилебровсебуттон

Отображает кнопку обзора в текущем элементе управления "Обзор" и помещает элемент управления в режим *просмотра файла* .

```
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>Параметры

*лпсздефекст*<br/>
Указывает расширение имени файла по умолчанию, используемое в диалоговом окне выбора файла. Значение по умолчанию — NULL.

*лпсзфилтер*<br/>
Указывает строку фильтра по умолчанию, используемую в диалоговом окне выбора файла. Значение по умолчанию — NULL.

*dwFlags*<br/>
Флаги диалогового окна. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов OFN_HIDEREADONLY и OFN_OVERWRITEPROMPT.

### <a name="remarks"></a>Примечания

Когда элемент управления "Обзор" находится в режиме поиска файлов, а пользователь нажимает кнопку обзора, элемент управления отображает стандартное диалоговое окно выбора файла.

Полный список доступных флагов см. в разделе [Структура OpenFileName](/windows/win32/api/commdlg/ns-commdlg-openfilenamew).

##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl:: Енаблефолдербровсебуттон

Отображает кнопку обзора в текущем элементе управления "Обзор" и помещает элемент управления в режим *просмотра папки* .

```
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Примечания

Если элемент управления "Обзор" находится в режиме просмотра папки и пользователь нажимает кнопку "Обзор", элемент управления отображает стандартное диалоговое окно "Выбор папки".

##  <a name="getmode"></a>CMFCEditBrowseCtrl:: Мода

Возвращает режим просмотра текущего элемента управления "Обзор".

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления, указывающее текущий режим элемента управления "Обзор". Режим просмотра определяет, отображает ли платформа кнопку обзора и какое действие происходит при нажатии пользователем этой кнопки.

В следующей таблице перечислены возможные возвращаемые значения.

|Значение|Описание|
|-----------|-----------------|
|`BrowseMode_Default`|**Пользовательский режим**. Выполняется определенное программистом действие.|
|`BrowseMode_File`|**Файловый режим**. Откроется диалоговое окно стандартный обозреватель файлов.|
|`BrowseMode_Folder`|**режим папки**. Откроется стандартное диалоговое окно Обозреватель папок.|
|`BrowseMode_None`|Кнопка Обзор не отображается.|

### <a name="remarks"></a>Примечания

По умолчанию `CMFCEditBrowseCtrl` объект инициализируется в `BrowseMode_None` режиме. Измените режим просмотра с помощью методов [CMFCEditBrowseCtrl:: енаблебровсебуттон](#enablebrowsebutton), [CMFCEditBrowseCtrl:: енаблефилебровсебуттон](#enablefilebrowsebutton)и [CMFCEditBrowseCtrl:: енаблефолдербровсебуттон](#enablefolderbrowsebutton) .

##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl:: Онафтерупдате

Вызывается структурой после обновления элемента управления "Обзор" с результатом действия "Обзор".

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать пользовательское действие.

##  <a name="onbrowse"></a>CMFCEditBrowseCtrl:: OnBrowse

Вызывается структурой после того, как пользователь нажмет кнопку "Обзор" элемента управления "Обзор".

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Примечания

Этот метод используется для выполнения пользовательского кода при нажатии пользователем кнопки обзора элемента управления "Обзор". Создайте класс, производный от `CMFCEditBrowseCtrl` класса, и переопределите его `OnBrowse` метод. В этом методе реализуйте пользовательское действие обзора и при необходимости обновите текстовое поле элемента управления "Обзор". В приложении используйте метод [енаблебровсебуттон](#enablebrowsebutton) для размещения элемента управления "Обзор" в пользовательском режиме *просмотра* .

##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl:: Ончанжелайаут

Перерисовывает текущий элемент управления "Обзор" для редактирования.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод при изменении режима просмотра элемента управления "Просмотр". Дополнительные сведения см. в разделе [CMFCEditBrowseCtrl:: onmode](#getmode).

##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl:: Ондравбровсебуттон

Вызывается платформой для рисования кнопки обзора в элементе управления "Обзор".

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства.

*Прямоугольник*<br/>
Ограничивающий прямоугольник кнопки обзора.

*бисбуттонпрессед*<br/>
Значение TRUE, если кнопка нажата; в противном случае — значение FALSE.

*бисбуттонхот*<br/>
Значение TRUE, если кнопка выделена; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Переопределите эту функцию в производном классе, чтобы настроить внешний вид кнопки обзора.

##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl:: Сетбровсебуттонимаже

Задает пользовательский образ на кнопке Обзор элемента управления "Обзор".

```
void SetBrowseButtonImage(
    HICON hIcon,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(UINT uiBmpResId);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
Маркер значка.

*хбитмап*<br/>
Маркер точечного рисунка.

*уибмпресид*<br/>
Идентификатор ресурса точечного рисунка.

*баутодестрой*<br/>
Значение TRUE, чтобы удалить указанный значок или точечный рисунок при выходе из этого метода; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Используйте этот метод для применения пользовательского изображения к кнопке обзора. По умолчанию платформа получает стандартный образ, когда элемент управления просмотром редактирования находится в режиме просмотра или просмотра *папок* .

##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl:: Ониллегалфиленаме

Вызвано структурой, когда в элементе управления "поле ввода" было указано недопустимое имя файла.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Параметры

*strFileName*<br/>
Указывает недопустимое имя файла.

### <a name="return-value"></a>Возвращаемое значение

Должен возвращать значение FALSE, если это имя файла не может быть передано в диалоговое окно файла. В этом случае фокус передается обратно в элемент управления Edit, и пользователь должен продолжить редактирование. Реализация по умолчанию отображает окно сообщения, уведомляющее пользователя о недопустимом имени файла и возвращающее значение FALSE. Этот метод можно переопределить, исправить имя файла и возвращать значение TRUE для дальнейшей обработки.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
