---
title: Класс CMFCAcceleratorKeyAssignCtrl
ms.date: 10/18/2018
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
ms.openlocfilehash: bd096657de56c0b6daa07004a927b92f1293ddf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454422"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>Класс CMFCAcceleratorKeyAssignCtrl

`CMFCAcceleratorKeyAssignCtrl` Класс расширяет [класс CEdit](../../mfc/reference/cedit-class.md) для поддержки дополнительных системных, таких как ALT, CONTROL и SHIFT.

## <a name="syntax"></a>Синтаксис

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Создает объект `CMFCAcceleratorKeyAssignCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Извлекает `ACCEL` структуру для сочетания клавиш, нажатого в объекте `CMFCAcceleratorKeyAssignCtrl`.|
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Определяет, задано ли сочетание клавиш.|
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Сбрасывает сочетание клавиш.|

## <a name="remarks"></a>Примечания

Этот класс расширяет функциональность класса `CEdit` благодаря поддержке сочетаний клавиш. `CMFCAcceleratorKeyAssignCtrl` Класса функции как [класс CEdit](../../mfc/reference/cedit-class.md) и он также может распознавать системные клавиши.

Этот класс сопоставляет физические сочетания клавиш со строковыми значениями. Например, пусть сочетание клавиш ALT+B сопоставлено со строкой "Alt + B". Когда пользователь нажимает это сочетание клавиш в объекте `CMFCAcceleratorKeyAssignCtrl`, отображается строка "Alt + B". Дополнительные сведения о сопоставлении сочетаний клавиш и формат строки см. в разделе [класс CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md).

## <a name="example"></a>Пример

В этом примере демонстрируется создание объекта `CMFCAcceleratorKeyAssignCtrl` и использование его метода `ResetKey` для сброса сочетания клавиш.

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxacceleratorkeyassignctrl.h

##  <a name="cmfcacceleratorkeyassignctrl"></a>  CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl

Создает [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) объекта.

```
CMFCAcceleratorKeyAssignCtrl();
```

##  <a name="getaccel"></a>  CMFCAcceleratorKeyAssignCtrl::GetAccel

Извлекает `ACCEL` структуру для сочетания клавиш, нажатого в [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) объекта.

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>Возвращаемое значение

`ACCEL` Структура, описывающая сочетание клавиш.

### <a name="remarks"></a>Примечания

Эта функция используется для получения `ACCEL` структуру для сочетания клавиш, введенные пользователем в вашей `CMFCAcceleratorKeyAssignCtrl` объекта.

##  <a name="isfocused"></a>  CMFCAcceleratorKeyAssignCtrl::IsFocused

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="iskeydefined"></a>  CMFCAcceleratorKeyAssignCtrl::IsKeyDefined

Определяет, определен ли сочетания клавиш в [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) объекта.

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь нажал уже является допустимым сочетанием клавиш, которые определяют сочетания клавиш; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция позволяет определить, является ли пользователь ввел допустимый сочетания клавиш в вашей `CMFCAcceleratorKeyAssignCtrl` объекта. Если сочетание клавиш существует, вы можете использовать [CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel) метод, чтобы получить `ACCEL` структуры, связанные с этого сочетания клавиш.

##  <a name="pretranslatemessage"></a>  CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

[in] *pMsg*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="resetkey"></a>  CMFCAcceleratorKeyAssignCtrl::ResetKey

Сбрасывает сочетание клавиш.

```
void ResetKey();
```

### <a name="remarks"></a>Примечания

Функция сбрасывает текст в элементе управления редактирования. Сюда входят любые сочетания клавиш, нажата.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)
