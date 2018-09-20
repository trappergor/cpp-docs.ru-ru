---
title: Класс CColorDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63b909c80ab8f2f8f5bd1c5ad002f2c5f6523081
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441048"
---
# <a name="ccolordialog-class"></a>Класс CColorDialog

Позволяет включить диалоговое окно выделения цветом в приложение.

## <a name="syntax"></a>Синтаксис

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CColorDialog::CColorDialog](#ccolordialog)|Создает объект `CColorDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CColorDialog::DoModal](#domodal)|Отображает диалоговое окно цвета и позволяет пользователю сделать выбор.|
|[CColorDialog::GetColor](#getcolor)|Возвращает `COLORREF` структуру, содержащую значения выбранного цвета.|
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Извлекает пользовательских цветов, созданных пользователем.|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Заставляет выбранный цвет для указанного цвета.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|Переопределите для проверки введенных в диалоговом окне цвет.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|Структура, используемая для настройки параметров диалогового окна.|

## <a name="remarks"></a>Примечания

Объект `CColorDialog` объект представляет собой диалоговое окно со списком цветов, которые определены для отображения системы. Пользователя можно выбрать или создать определенного цвета из списка, которой затем сообщается обратно в приложение при выходе из диалоговое окно.

Для создания `CColorDialog` объекта, используйте предоставленный конструктор, или создании нового производного класса и использовать собственный пользовательский конструктор.

После создания диалоговом окне можно задать или изменить значения в [m_cc](#m_cc) структуры для инициализации значений элементов управления диалогового окна. *M_cc* структуры имеет тип [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora).

После инициализации элементов управления диалогового окна, вызовите `DoModal` функция-член отображается диалоговое окно и позволяет пользователю выбрать цвет. `DoModal` Возвращает выбор пользователем кнопки ОК (IDOK) или Отмена (IDCANCEL) либо диалогового окна.

Если `DoModal` возвращает IDOK, можно использовать один из `CColorDialog`в функции-члены для получения сведений, введенное пользователем.

Можно использовать Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) функция для определения, произошла ли ошибка во время инициализации диалогового окна и Дополнительные сведения об ошибке.

`CColorDialog` использует COMMDLG. DLL-файл, который поставляется с Windows 3.1 и более поздних версиях.

Чтобы настроить в диалоговом окне, являются производными от класса `CColorDialog`, предоставляют шаблон настраиваемое диалоговое окно и добавить схему сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны передаваться в базовый класс.

Настройка функция-обработчик не является обязательным.

> [!NOTE]
>  В некоторых установках `CColorDialog` объект не будет отображаться на сером фоне, при использовании платформы вносить другие `CDialog` объекты серого цвета.

Дополнительные сведения об использовании `CColorDialog`, см. в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog

Создает объект `CColorDialog`.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*clrInit*<br/>
Выбранный цвет по умолчанию. Если значение не указано, по умолчанию используется RGB(0,0,0) (черный).

*dwFlags*<br/>
Набор флагов, которые настраивать функции и внешний вид диалогового окна. Дополнительные сведения см. в разделе [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora) структуры в пакете Windows SDK.

*pParentWnd*<br/>
Указатель на окно родительский объект или владельца диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

##  <a name="domodal"></a>  CColorDialog::DoModal

Вызывайте эту функцию для отображения диалогового окна Windows распространенных цвет и разрешить пользователю выбрать цвет.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK и IDCANCEL. Если возвращается IDCANCEL, вызовите Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) функцию, чтобы определить, произошла ли ошибка.

IDOK и IDCANCEL являются константы, указывающие, является ли пользователь выбрал кнопку ОК или "Отмена".

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные параметры диалогового окна цвет путем определения участников [m_cc](#m_cc) структуры, это следует сделать до вызова метода `DoModal` , но после создания объекта диалогового окна.

После вызова метода `DoModal`, можно вызвать другой член функции, чтобы получить параметры или данные, введенные пользователем в диалоговом окне.

### <a name="example"></a>Пример

  См. в примере [CColorDialog::CColorDialog](#ccolordialog).

##  <a name="getcolor"></a>  CColorDialog::GetColor

Вызывайте эту функцию после вызова метода `DoModal` для получения сведений о цвете выбрал пользователь.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COLORREF](/windows/desktop/gdi/colorref) значение, содержащее данные RGB для цвета, выбранного в диалоговом окне цвет.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors

`CColorDialog` объекты разрешить пользователю, помимо выбора цвета, определение пользовательских цветов, 16.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив 16 цветовых значений RGB, сохраняет пользовательские цвета, созданных пользователем.

### <a name="remarks"></a>Примечания

`GetSavedCustomColors` Функция-член обеспечивает доступ к эти цвета. Эти цвета можно получить после [DoModal](#domodal) возвращает IDOK.

Каждое из 16 значений RGB в возвращенном массиве инициализируется RGB(255,255,255) (белый переключатель). Пользовательские цвета, выбранные пользователем, сохраняются только между вызовами поле диалогового окна в приложении. Если вы хотите сохранить эти цвета между вызовами приложения, необходимо сохранить их в других целях, например в инициализацию (. Файл INI).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

##  <a name="m_cc"></a>  CColorDialog::m_cc

Структура типа [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora), члены которой хранения характеристики и значения диалогового окна.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Примечания

После построения `CColorDialog` объекта, можно использовать *m_cc* для задания различных аспектов диалоговом окне перед вызовом [DoModal](#domodal) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

##  <a name="oncolorok"></a>  CColorDialog::OnColorOK

Переопределите для проверки введенных в диалоговом окне цвет.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если диалоговое окно не должно быть закрыто; в противном случае — 0, чтобы принять цвет, который был введен.

### <a name="remarks"></a>Примечания

Переопределите эту функцию только в том случае, если вы хотите предоставить пользовательскую проверку цвета, выбранного пользователем в диалоговом окне цвет.

Пользователь может выбрать цвет одним из следующих двух способов:

- Если щелкнуть цвет в палитре цветов. Затем отображаются значения RGB для выбранного цвета в соответствующие поля ввода RGB.

- Вводя значения в RGB текстовых полей

Переопределение `OnColorOK` позволяет отклонять цвета, пользователь вводит в общем диалоговом окне цвет по любой причине конкретного приложения.

Как правило вы не обязательно должны использовать эту функцию, так как платформа обеспечивает проверку по умолчанию цвета и отображает окно сообщения, если введено недопустимое цвета.

Можно вызвать [SetCurrentColor](#setcurrentcolor) изнутри `OnColorOK` для принудительного выбора цвета. Один раз `OnColorOK` произошло (то есть пользователь нажимает кнопку **ОК** чтобы принять изменение цвета), можно вызвать [GetColor](#getcolor) для получения значения RGB для нового цвета.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor

Вызывайте эту функцию после вызова метода `DoModal` для принудительного текущего выделения цвета значение цвета, указанные в *clr*.

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Среда CLR*<br/>
Значение цвета RGB.

### <a name="remarks"></a>Примечания

Эта функция вызывается из обработчика сообщений или `OnColorOK`. Диалоговое окно автоматически обновит выбора пользователя, на основе значения из *clr* параметра.

### <a name="example"></a>Пример

  См. в примере [CColorDialog::OnColorOK](#oncolorok).

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../visual-cpp-samples.md)<br/>
[Пример MFC ФУНКЦИЙ](../../visual-cpp-samples.md)<br/>
[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

