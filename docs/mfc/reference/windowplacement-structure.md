---
title: Структура WINDOWPLACEMENT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b163d93de22d313d72ca5dbfd384788077ae1b01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447281"
---
# <a name="windowplacement-structure"></a>Структура WINDOWPLACEMENT

`WINDOWPLACEMENT` Структура содержит сведения о размещении окна на экране.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagWINDOWPLACEMENT {     /* wndpl */
    UINT length;
    UINT flags;
    UINT showCmd;
    POINT ptMinPosition;
    POINT ptMaxPosition;
    RECT rcNormalPosition;
} WINDOWPLACEMENT;
```

#### <a name="parameters"></a>Параметры

*length*<br/>
Задает длину в байтах, структуры.

*flags*<br/>
Указывает флаги, определяющие положение свернутого окна и метод, по которому окно восстановлено. Этот член может иметь один или оба из следующих флагов:

- WPF_SETMINPOSITION указывает, что можно указать x - и y позиции свернутого окна. Этот флаг должен быть указан, если координаты задаются в `ptMinPosition` член.

- WPF_RESTORETOMAXIMIZED указывает, что восстановленные окна будет развернуть, независимо от того, является ли он было максимальным, прежде чем он был свернут. Этот параметр допустим только в следующий раз окно восстановлено. Это не приводит к изменению восстановления по умолчанию. Этот флаг допустим только в том случае, если указано значение SW_SHOWMINIMIZED для `showCmd` член.

*showCmd*<br/>
Указывает текущее состояние отображения окна. Этот член может принимать одно из следующих значений:

- SW_HIDE скрывает окно и передает активации на другое окно.

- SW_MINIMIZE сворачивает указанное окно и активирует окно верхнего уровня в списке системы.

- SW_RESTORE активирует и отображает окно. Если окно свернуто или развернуто, Windows восстанавливает его исходный размер и положение (аналогично SW_SHOWNORMAL).

- SW_SHOW активирует окно и отображает его в его текущего размера и положения.

- SW_SHOWMAXIMIZED активирует окно и отображает его в виде развернутого окна.

- SW_SHOWMINIMIZED активирует окно и отображает его в виде значка.

- SW_SHOWMINNOACTIVE вывод окна в виде значка. Окно, который сейчас активен остается активным.

- SW_SHOWNA отображает окно в ее текущем состоянии. Окно, который сейчас активен остается активным.

- SW_SHOWNOACTIVATE отображает окно в свои последние размер и положение. Окно, который сейчас активен остается активным.

- SW_SHOWNORMAL активирует и отображает окно. Если окно свернуто или развернуто, Windows восстанавливает его исходный размер и положение (аналогично SW_RESTORE).

*ptMinPosition*<br/>
Задает положение верхнего левого угла окна, если окно свернуто.

*ptMaxPosition*<br/>
Задает положение верхнего левого угла окна, если окно развернуто.

*rcNormalPosition*<br/>
Задает координаты окна, когда это окно находится в обычного положения (восстановленной).

## <a name="requirements"></a>Требования

**Заголовок:** winuser.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

