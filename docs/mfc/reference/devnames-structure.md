---
title: Структура DEVNAMES | Документы Microsoft
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
ms.openlocfilehash: 3234df2f0430ea75399791f4fd88a636a63b67e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371482"
---
# <a name="devnames-structure"></a>Структура DEVNAMES
`DEVNAMES` Структура содержит строк, которые определяют драйвера, устройств и имена выходной порт принтера.  
  
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
 *wDriverOffset*  
 (Ввода вывода) Задает смещение в символах символом null строку, которая содержит имя файла драйвера устройства (без расширения). На входе эта строка используется для определения принтера, чтобы отобразить изначально, в диалоговом окне.  
  
 *wDeviceOffset*  
 (Ввода вывода) Задает смещение в символах символом null строку (не более 32 байта, включая значение null), содержащую имя устройства. Эта строка должна быть идентична **dmDeviceName** членом [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуры.  
  
 *wOutputOffset*  
 (Ввода вывода) Задает смещение в символах для символом null строку, содержащую имя устройства DOS, для вывода физического носителя (выходной порт).  
  
 *wDefault*  
 Указывает, содержится ли в строке `DEVNAMES` структуры идентификации принтер по умолчанию. Эта строка используется для проверки того, что принтер по умолчанию не изменился с момента последней операции печати. Для ввода, если **DN_DEFAULTPRN** флаг установлен, другие значения `DEVNAMES` структуры проверяются принтера. Если любой из строк не совпадают, предупреждающее сообщение отображается, сообщая пользователю, возможно, необходимо изменить документ. На выходе **wDefault** элемент изменяется только в том случае, если отображается диалоговое окно «Параметры печати» и пользователь выбрал кнопки «ОК». **DN_DEFAULTPRN** флаг устанавливается в том случае, если был установлен принтер по умолчанию. При выборе конкретного принтера не установлен флаг. Все биты в этом члене зарезервированы для внутреннего использования процедуру диалогового окна печати.  
  
## <a name="remarks"></a>Примечания  
 **PrintDlg** функция использует эти строки в инициализации членов в системные диалоговое окно печати. Когда пользователь закрывает диалоговое окно, возвращаются сведения о выбранном принтере в этой структуре.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** commdlg.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)


