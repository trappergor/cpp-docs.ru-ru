---
title: Класс CColorDialog
ms.date: 11/04/2016
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
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
ms.openlocfilehash: 99b4ff27a7686972bcbc85478998b52ed713ab5b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754257"
---
# <a name="ccolordialog-class"></a>Класс CColorDialog

Позволяет включить в приложение диалоговую коробку выбора цвета.

## <a name="syntax"></a>Синтаксис

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CColorДиалог::CColorДиалог](#ccolordialog)|Формирует объект `CColorDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CColorДиалог::DoModal](#domodal)|Отображает цветную диалоговую коробку и позволяет пользователю сделать выбор.|
|[CColorДиалог::GetColor](#getcolor)|Возвращает `COLORREF` структуру, содержащую значения выбранного цвета.|
|[CColorДиалог::GetSavedCustomColors](#getsavedcustomcolors)|Извлекает пользовательские цвета, созданные пользователем.|
|[CColorДиалог::SetCurrentColor](#setcurrentcolor)|Принуждает текущий выбор цвета к указанному цвету.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CColorDialog:OnColorOK](#oncolorok)|Переопределение для проверки цвета, внесенного в диалоговую будку.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CColorДиалог::m_cc](#m_cc)|Структура, используемая для настройки настроек диалогового окна.|

## <a name="remarks"></a>Remarks

Объект `CColorDialog` представляет собой диалоговую коробку со списком цветов, которые определены для системы отображения. Пользователь может выбрать или создать определенный цвет из списка, который затем сообщается обратно в приложение, когда диалоговая коробка выходит.

Чтобы построить объект, используйте предоставленный `CColorDialog` конструктор или получите новый класс и используйте свой собственный пользовательский конструктор.

После построения диалогового окна можно установить или изменить любые значения в структуре [m_cc](#m_cc) для инициализации значений элементов управления диалогового окна. Структура *m_cc* типа [CHOOSECOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1).

После инициализации элементов управления `DoModal` диалоговой будкой позвоните функции участника для отображения диалогового окна и позвольте пользователю выбрать цвет. `DoModal`возвращает пользователю выбор кнопки OK (IDOK) или кнопки «Отмена» (IDCANCEL).

При `DoModal` возврате IDOK можно `CColorDialog`использовать одну из функций участника для получения информации, вводимых пользователем.

Вы можете использовать функцию Windows [CommDlgExtendedError,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) чтобы определить, произошла ли ошибка во время инициализации диалогового окна, и узнать больше об ошибке.

`CColorDialog`опирается на COMMDLG. DLL файл, который поставляется с версиями Windows 3.1 и позже.

Чтобы настроить диалоговое окно, вывежьте класс из, `CColorDialog`предоставьте пользовательский шаблон диалогов и добавьте карту сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны передаваться базовому классу.

Настройка функции крючка не требуется.

> [!NOTE]
> На некоторых `CColorDialog` установках объект не будет отображаться с серым `CDialog` фоном, если вы использовали фреймворк для того, чтобы сделать другие объекты серыми.

Для получения дополнительной `CColorDialog`информации об использовании см. [Common Dialog Classes](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="ccolordialogccolordialog"></a><a name="ccolordialog"></a>CColorДиалог::CColorДиалог

Формирует объект `CColorDialog`.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*clrInit*<br/>
Выбор цвета по умолчанию. Если значение не указано, по умолчанию RGB (0,0,0) (черный).

*dwFlags*<br/>
Набор флагов, настраивающие функцию и внешний вид диалогового окна. Для получения дополнительной [информации](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1) см.

*pParentWnd*<br/>
Указатель на родительское или владельца окна диалогового окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

## <a name="ccolordialogdomodal"></a><a name="domodal"></a>CColorДиалог::DoModal

Вызовите эту функцию для отображения общего цветного диалога Windows и позвольте пользователю выбрать цвет.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK или IDCANCEL. Если IDCANCEL возвращается, позвоните в функцию Windows [CommDlgExtendedError,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) чтобы определить, произошла ли ошибка.

IDOK и IDCANCEL являются константами, указывающими на то, выбрал ли пользователь кнопку OK или Cancel.

### <a name="remarks"></a>Remarks

Если вы хотите инициализировать различные параметры диалогового ящика цвета, установив `DoModal` члены [структуры m_cc,](#m_cc) вы должны сделать это перед вызовом, но после построения объекта диалогового ящика.

После `DoModal`вызова можно вызвать другие функции участника, чтобы получить настройки или ввод информации пользователем в диалоговую будку.

### <a name="example"></a>Пример

  Смотрите пример [CColorDialog::CColorDialog](#ccolordialog).

## <a name="ccolordialoggetcolor"></a><a name="getcolor"></a>CColorДиалог::GetColor

Вызов исчерпайте эту функцию после вызова, `DoModal` чтобы получить информацию о выбранном пользователем цвете.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF,](/windows/win32/gdi/colorref) содержащее информацию О РГБ для цвета, выбранного в цветном диалоговом поле.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

## <a name="ccolordialoggetsavedcustomcolors"></a><a name="getsavedcustomcolors"></a>CColorДиалог::GetSavedCustomColors

`CColorDialog`объекты позволяют пользователю, в дополнение к выбору цветов, определить до 16 пользовательских цветов.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив из 16 значений цвета RGB, который хранит пользовательские цвета, созданные пользователем.

### <a name="remarks"></a>Remarks

Функция `GetSavedCustomColors` члена обеспечивает доступ к этим цветам. Эти цвета могут быть извлечены после того, как [DoModal](#domodal) возвращает IDOK.

Каждое из 16 значений RGB в возвращенном массиве инициализировано до RGB (255 255 255) (белый). Пользовательские цвета, выбранные пользователем, сохраняются только между вызовами в диалоговом поле в приложении. Если вы хотите сохранить эти цвета между вызовами приложения, вы должны сохранить их каким-то другим способом, например, в инициализации (. INI) файл.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

## <a name="ccolordialogm_cc"></a><a name="m_cc"></a>CColorДиалог::m_cc

Структура типа [CHOOSECOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1), члены которой хранят характеристики и значения диалогового окна.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Remarks

После построения `CColorDialog` объекта можно использовать *m_cc* для настройки различных аспектов диалогового окна перед вызовом функции члена [DoModal.](#domodal)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

## <a name="ccolordialogoncolorok"></a><a name="oncolorok"></a>CColorDialog:OnColorOK

Переопределение для проверки цвета, внесенного в диалоговую будку.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если диалоговая будка не должна быть уволена; в противном случае 0 принять цвет, который был введен.

### <a name="remarks"></a>Remarks

Переопределить эту функцию только в том случае, если вы хотите обеспечить пользовательскую проверку цвета, выбранного пользователем в цветном диалоговом поле.

Пользователь может выбрать цвет одним из следующих двух методов:

- Нажав на цвет на цветовую палитру. Значения RGB выбранного цвета затем отражаются в соответствующих коробках для отобрачения RGB.

- Ввод значений в ящиках для отсваки RGB

Переопределение `OnColorOK` позволяет отклонить цвет, который пользователь вводит в общую цветовую поле для диалога по любой причине, конкретной для приложения.

Обычно эта функция не требуется, поскольку фреймворк обеспечивает проверку цветов по умолчанию и отображает поле сообщения при входе недействительного цвета.

Вы можете вызвать [SetCurrentColor](#setcurrentcolor) изнутри, `OnColorOK` чтобы заставить выбор цвета. После `OnColorOK` того, как был уволен (то есть, пользователь нажимает **OK,** чтобы принять изменение цвета), вы можете вызвать [GetColor,](#getcolor) чтобы получить значение RGB нового цвета.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

## <a name="ccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CColorДиалог::SetCurrentColor

Вызов ими `DoModal` функции после вызова, чтобы заставить текущий выбор цвета к цветовому значению, указанному в *clr.*

```cpp
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Параметры

*Clr*<br/>
Значение цвета RGB.

### <a name="remarks"></a>Remarks

Эта функция вызывается изнутри `OnColorOK`обработчика сообщений или . Диалоговое поле автоматически обновляет выбор пользователя в зависимости от значения параметра *clr.*

### <a name="example"></a>Пример

  Смотрите пример [CColorDialog::OnColorOK](#oncolorok).

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[Класс CCommonДиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
