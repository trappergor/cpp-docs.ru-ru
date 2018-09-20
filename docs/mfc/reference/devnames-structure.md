---
title: Структура DEVNAMES | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES [MFC]
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 637843873bbb0e12a76168bd08b613e14b391ef8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392467"
---
# <a name="devnames-structure"></a>Структура DEVNAMES

`DEVNAMES` Структура содержит строки, которые определяют драйверов, устройство и имена выходной порт принтера.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagDEVNAMES { /* dvnm */
    WORD wDriverOffset;
    WORD wDeviceOffset;
    WORD wOutputOffset;
    WORD wDefault; */* driver,
    device,
    and port-name strings follow wDefault */
} DEVNAMES;
```

#### <a name="parameters"></a>Параметры

*wDriverOffset*<br/>
(Ввода вывода) Задает смещение в символах для нулем строка, содержащая имя файла драйвера устройства (без расширения). Во входных данных эта строка используется для определения принтера изображался в диалоговом окне.

*wDeviceOffset*<br/>
(Ввода вывода) Задает смещение в символах для заканчивающуюся нулем строку (не более 32 байта, включая нуль), содержащая имя устройства. Эта строка должна быть идентична `dmDeviceName` членом [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) структуры.

*wOutputOffset*<br/>
(Ввода вывода) Задает смещение в символах для заканчивающуюся нулем строку, содержащую имя устройства DOS для физических выходному носителю (выходной порт).

*wDefault*<br/>
Указывает, содержится ли строки в `DEVNAMES` структуру определения принтер по умолчанию. Эта строка используется для проверки того, что принтер по умолчанию не изменился с момента последней операции печати. Во входных данных, если флаг DN_DEFAULTPRN другого значения в `DEVNAMES` структура проходят проверку на соответствие текущего принтера по умолчанию. Если любой из строк не совпадают, выводится предупреждающее сообщение, в сообщая пользователю, что документ может потребоваться для переформатирования. На выводе `wDefault` элемент изменяется только в том случае, если было отображено диалоговое окно «Параметры печати», и пользователь нажимает кнопку «OK». Флаг DN_DEFAULTPRN устанавливается в том случае, если был установлен принтер по умолчанию. Если установлен принтер, флаг не установлен. Все остальные биты в этом члене зарезервированы для внутреннего использования, процедура диалогового окна печати.

## <a name="remarks"></a>Примечания

`PrintDlg` Функция использует эти строки в инициализации членов в системный диалоговое окно печати. Когда пользователь закрывает диалоговое окно, в этой структуре возвращаются сведения о выбранном принтере.

## <a name="requirements"></a>Требования

**Заголовок:** commdlg.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)


