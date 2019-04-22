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
ms.openlocfilehash: 0c6fb39e17e22bcac60d50b87f7370c6a9f91db9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58770682"
---
# <a name="cmfceditbrowsectrl-class"></a>Класс CMFCEditBrowseCtrl

`CMFCEditBrowseCtrl` Класс поддерживает управления обзор редактирования, который является редактируемых текстовых полей, которые дополнительно содержат кнопку обзора. Когда пользователь нажимает кнопку обзора, элемент управления выполняет настраиваемое действие или отображает стандартное диалоговое окно, содержащее браузер файла или папки в браузере.

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
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Включает или отключает (скрытие) кнопку обзора.|
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Активирует кнопку обзора и помещает Обзор элемента управления редактирования в *Обзор файлов* режим.|
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Активирует кнопку обзора и помещает Обзор элемента управления редактирования в *поиск папки* режим.|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Возвращает текущий режим обзора.|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Вызвано структурой после редактирования элемента управления обзора обновляется с результатом действия обзора.|
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Вызвано структурой после нажатия кнопки «Обзор».|
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Перерисовывает текущего элемента управления обзора редактирования.|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Вызвано структурой для прорисовки кнопки обзора.|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Вызывается платформой, если было введено недопустимое имя файла в элементе управления.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) функции Windows. Синтаксис и Дополнительные сведения см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Задает пользовательский образ для кнопки "Обзор".|

## <a name="remarks"></a>Примечания

Используйте элемент управления редактированием обзора, чтобы выбрать имя файла или папки. При необходимости используйте элемент управления для выполнения настраиваемого действия, например, чтобы отобразить диалоговое окно. Можно отобразить или не отображает кнопку обзора, и можно применить пользовательскую метку или изображение на кнопке.

*Режим просмотра* обзора редактирования элемента управления определяет, отображается ли кнопка обзора и какое действие происходит при нажатии кнопки. Дополнительные сведения см. в разделе [GetMode](#getmode) метод.

`CMFCEditBrowseCtrl` Класс поддерживает следующие режимы.

- **пользовательский режим**

   Настраиваемое действие выполняется в том случае, когда пользователь нажимает кнопку обзора. Например можно отобразить диалоговое окно для конкретного приложения.

- **режим файла**

   Диалоговое окно выбора стандартный файл отображается в том случае, когда пользователь нажимает кнопку обзора.

- **режиме папки**

   Диалоговое окно выбора стандартные папки отображается в том случае, когда пользователь нажимает кнопку обзора.

## <a name="how-to-specify-an-edit-browse-control"></a>Руководство. Укажите элемент управления редактированием обзора

Выполните следующие действия, чтобы включить элемент управления редактирования обзора в приложении.

1. Если вы хотите применить режим настраиваемый поиск, собственный производный класс от `CMFCEditBrowseCtrl` класса и затем Переопределите [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) метод. В переопределенном методе выполнить пользовательское действие просмотра и обновления Обзор элемента управления редактирования результатом.

1. Внедрение либо `CMFCEditBrowseCtrl` объект или объект элемента управления обзора производном редактирования в родительский объект окна.

1. Если вы используете **мастер классов** для создания диалогового окна, добавьте элемент управления редактированием ( `CEdit`) в форме диалогового окна. Кроме того Добавьте переменную для доступа к элементу управления в файле заголовка. В файле заголовка, измените тип переменной из `CEdit` для `CMFCEditBrowseCtrl`. Обзор элемента управления редактирования будут создаваться автоматически. Если вы не используете **мастер классов**, добавьте `CMFCEditBrowseCtrl` переменной в файл заголовка и затем вызвать его `Create` метод.

1. При добавлении элемента управления обзора в диалоговое окно, используйте **ClassWizard** средство для настройки обмена данными.

1. Вызовите [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), или [EnableBrowseButton](#enablebrowsebutton) метод для установки в режиме просмотра и отображения кнопки "Обзор". Вызовите [GetMode](#getmode) метод, чтобы получить текущий режим обзора.

1. Чтобы предоставить настраиваемый образ для кнопки "Обзор", вызовите [SetBrowseButtonImage](#setbrowsebuttonimage) метода или переопределение [OnDrawBrowseButton](#ondrawbrowsebutton) метод.

1. Чтобы удалить кнопку из элемента управления обзора редактирования, вызовите [EnableBrowseButton](#enablebrowsebutton) метод с *bEnable* параметр значение FALSE.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Пример

Приведенный ниже показано, как использовать два метода в `CMFCEditBrowseCtrl` класса: `EnableFolderBrowseButton` и `EnableFileBrowseButton`. Этот пример является частью [пример новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxeditbrowsectrl.h

##  <a name="enablebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableBrowseButton

Отображает или не отображает кнопку обзора для текущего элемента управления обзора редактирования.

```
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Значение TRUE для отображения кнопки "Обзор"; Значение FALSE, если не требуется отображать кнопку обзора. Значение по умолчанию — TRUE.

*szLabel*<br/>
Метка, которая отображается на кнопке обзора. Значение по умолчанию — " **...** ".

### <a name="remarks"></a>Примечания

Если *bEnable* параметр имеет значение TRUE, следует реализовать настраиваемое действие, выполняемое при нажатии кнопки обзора. Чтобы реализовать настраиваемое действие, наследуйте класс от `CMFCEditBrowseCtrl` класса и затем переопределить ее [OnBrowse](#onbrowse) метод.

Если *bEnable* параметра равно TRUE, в режиме просмотра элемента управления `BrowseMode_Default`; в противном случае — в режиме просмотра `BrowseMode_None`. Дополнительные сведения о режимах просмотра см. в разделе [GetMode](#getmode) метод.

##  <a name="enablefilebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFileBrowseButton

Отображает кнопку обзора для текущего элемента управления обзора редактирования и переводит элемент управления *Обзор файлов* режим.

```
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>Параметры

*lpszDefExt*<br/>
Указывает расширение имени файла по умолчанию, используемое в диалоговом окне выбора файла. Значение по умолчанию имеет значение NULL.

*lpszFilter*<br/>
Указывает строку фильтра по умолчанию, используемую в диалоговом окне выбора файла. Значение по умолчанию имеет значение NULL.

*dwFlags*<br/>
Флаги диалогового окна. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов OFN_HIDEREADONLY и OFN_OVERWRITEPROMPT.

### <a name="remarks"></a>Примечания

Когда элемент управления "Обзор" находится в режиме поиска файлов, а пользователь нажимает кнопку обзора, элемент управления отображает стандартное диалоговое окно выбора файла.

Полный список доступных флагов см. в разделе [структуры OPENFILENAME](/windows/desktop/api/commdlg/ns-commdlg-tagofna).

##  <a name="enablefolderbrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFolderBrowseButton

Отображает кнопку обзора для текущего элемента управления обзора редактирования и переводит элемент управления *поиск папки* режим.

```
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Примечания

Если поле ввода обзора находится в режиме просмотра папок и пользователь нажимает кнопку обзора, элемент управления отображает диалоговое окно выбора стандартные папки.

##  <a name="getmode"></a>  CMFCEditBrowseCtrl::GetMode

Извлекает режим просмотра текущего элемента управления обзора.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одно из значений перечисления, указывающее текущий режим правки Обзор элемента управления. В режиме просмотра определяет ли платформа отображает кнопку обзора и какое действие происходит, когда пользователь нажимает эту кнопку.

В следующей таблице перечислены возможные возвращаемые значения.

|Значение|Описание|
|-----------|-----------------|
|`BrowseMode_Default`|**пользовательский режим**. Действия, определяемые программистом выполняются.|
|`BrowseMode_File`|**режим файла**. Откроется диалоговое окно браузера стандартный файл.|
|`BrowseMode_Folder`|**режиме папки**. Откроется диалоговое окно браузера стандартные папки.|
|`BrowseMode_None`|«Обзор» не отображается.|

### <a name="remarks"></a>Примечания

По умолчанию `CMFCEditBrowseCtrl` инициализируется с `BrowseMode_None` режим. Изменения в режиме просмотра с [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), и [CMFCEditBrowseCtrl::EnableFolderBrowseButton ](#enablefolderbrowsebutton) методы.

##  <a name="onafterupdate"></a>  CMFCEditBrowseCtrl::OnAfterUpdate

Вызвано структурой после редактирования элемента управления обзора обновляется с результатом действия обзора.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, чтобы реализовать настраиваемое действие.

##  <a name="onbrowse"></a>  CMFCEditBrowseCtrl::OnBrowse

Вызвано структурой после нажатия кнопки "Обзор" Обзор элемента управления.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Примечания

Этот метод позволяет выполнять пользовательский код, когда пользователь нажимает кнопку обзора Обзор элемента управления. Собственный производный класс от `CMFCEditBrowseCtrl` класса и переопределять его `OnBrowse` метод. В этом методе реализовать пользовательское действие просмотра и при необходимости обновляет текстовое поле элемента управления обзора. В приложении, используйте [EnableBrowseButton](#enablebrowsebutton) метод для размещения элемента управления обзора редактирования в *настраиваемый поиск* режим.

##  <a name="onchangelayout"></a>  CMFCEditBrowseCtrl::OnChangeLayout

Перерисовывает текущего элемента управления обзора редактирования.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод при режиме просмотра для обзора редактирования управления изменениями. Дополнительные сведения см. в разделе [CMFCEditBrowseCtrl::GetMode](#getmode).

##  <a name="ondrawbrowsebutton"></a>  CMFCEditBrowseCtrl::OnDrawBrowseButton

Вызвано структурой для прорисовки кнопки обзора на обзор элемента управления редактирования.

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
Ограничивающий прямоугольник кнопку обзора.

*bIsButtonPressed*<br/>
Значение TRUE, если при нажатии кнопки; в противном случае — значение FALSE.

*bIsButtonHot*<br/>
Значение TRUE, если кнопка выделена; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Переопределите эту функцию в производном классе, чтобы настроить внешний вид «Обзор».

##  <a name="setbrowsebuttonimage"></a>  CMFCEditBrowseCtrl::SetBrowseButtonImage

Задает пользовательский образ на кнопке обзора Обзор элемента управления.

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
Дескриптор значка.

*hBitmap*<br/>
Дескриптор точечного рисунка.

*uiBmpResId*<br/>
Идентификатор ресурса растрового изображения.

*bAutoDestroy*<br/>
Значение TRUE, если для удаления указанного значка или точечного рисунка, если этот метод завершает работу; в противном случае — значение FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы применить пользовательский образ к «Обзор». По умолчанию платформа получает стандартного образа при Обзор элемента управления редактирования в *Обзор файлов* или *поиск папки* режим.

##  <a name="onillegalfilename"></a>  CMFCEditBrowseCtrl::OnIllegalFileName

Вызывается платформой, если было введено недопустимое имя файла в элементе управления.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Параметры

*strFileName*<br/>
Указывает недопустимое имя файла.

### <a name="return-value"></a>Возвращаемое значение

Должна возвращать значение FALSE, если это имя файла не могут быть переданы рамками диалоговое окно файла. В этом случае фокус перемещается обратно в элемент управления редактирования, и пользователь должен продолжить редактирование. Реализация по умолчанию отображает окно сообщения, сообщает пользователю о недопустимое имя файла и возвращает значение FALSE. Можно переопределить этот метод, исправьте имя файла и возвращает значение TRUE, для дальнейшей обработки.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
