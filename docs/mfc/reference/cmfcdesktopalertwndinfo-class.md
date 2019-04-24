---
title: Класс CMFCDesktopAlertWndInfo
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: a4b3d8769b3d267c0bd3f81269dd3b8ab3cf3184
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768293"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>Класс CMFCDesktopAlertWndInfo

`CMFCDesktopAlertWndInfo` Класс используется с [класс CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md). Определяет элементы управления, которые отображаются, если всплывает окно оповещения.

## <a name="syntax"></a>Синтаксис

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::operator=](#operator_eq)||

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Дескриптор для значка, который отображается.|
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Идентификатор команды, связанные со ссылкой на окно оповещения.|
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Текст, отображаемый на окно оповещения.|
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Ссылки, которая отображается на окно оповещения.|

## <a name="remarks"></a>Примечания

`CMFCDesktopAlertWndInfo` Передается класс [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) метод, чтобы задать элементы, которые отображаются в диалоговом окне по умолчанию окно оповещения. Диалоговое окно по умолчанию может содержать три элемента:

- Значок, который устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).

- Метки или текстового сообщения, которое устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).

- Связь, которая устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Чтобы задать команду, которая выполняется при нажатии на ссылку, вызовите [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).

Если диалоговое окно по умолчанию недостаточно, можно создать настраиваемое диалоговое окно и передать его в [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) метода вместо использования этого класса. Дополнительные сведения см. в разделе [класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Пример

В следующем примере демонстрируется использование различных элементов в `CMFCDesktopAlertWndInfo` класса. В примере, как задать дескриптор для значка, отображаемого, текст, отображаемый на окно оповещения, ссылки, которая отображается в окне предупреждения с рабочего стола и идентификатор команды, которая связана со ссылкой на окно оповещения. Этот пример является частью [Desktop оповещения демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDesktopAlertDialog.h

##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator=

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>Параметры

[in] *src*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="m_hicon"></a>  CMFCDesktopAlertWndInfo::m_hIcon

Дескриптор для значка, который отображается.

```
HICON m_hIcon;
```

### <a name="remarks"></a>Примечания

##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID

Идентификатор команды, связанные со ссылкой на окно оповещения.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>Примечания

Идентификатор команды отправляется владельцу всплывающего окна при нажатии на ссылке, указанной [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).

##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText

Текст, отображаемый на окно оповещения.

```
CString m_strText;
```

### <a name="remarks"></a>Примечания

##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL

Ссылки, которая отображается на окно оповещения.

```
CString m_strURL;
```

### <a name="remarks"></a>Примечания

Когда пользователь щелкает ссылку, команда, имеет [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) идентификатор команды, которые будут отправляться владельцу всплывающего окна.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)
