---
title: "Структура DEVNAMES | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 698a338c94dfa402dd51fa4f683b92a5d30cc0cd
ms.lasthandoff: 02/24/2017

---
# <a name="devnames-structure"></a>Структура DEVNAMES
`DEVNAMES` Структура содержит строк, которые определяют имена выходной порт принтера, устройства и драйвера.  
  
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
 (Ввода вывода) Задает смещение в символах нулем строку, которая содержит имя файла драйвера устройства (без расширения). На входе эта строка используется для определения принтера изображался в диалоговом окне.  
  
 *wDeviceOffset*  
 (Ввода вывода) Задает смещение в символах нулем строку (не более 32 байта, включая значение null), содержащую имя устройства. Эта строка должна быть идентична **dmDeviceName** членом [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуры.  
  
 *wOutputOffset*  
 (Ввода вывода) Задает смещение в символах нулем строку, которая содержит имя устройства DOS для вывода физического носителя (выходной порт).  
  
 *wDefault*  
 Указывает, содержится ли строки в `DEVNAMES` структуру определения принтер по умолчанию. Эта строка используется для проверки того, что принтер по умолчанию не изменился с момента последней операции печати. Для ввода, если **DN_DEFAULTPRN** флаг установлен, другие значения `DEVNAMES` структуру проверяются текущего принтера по умолчанию. Если любую из строк не совпадают, предупреждающее сообщение отображается, сообщая пользователю, что может потребоваться изменить документ. На выходе **wDefault** элемент изменяется только в том случае, если было открыто диалоговое окно Настройка печати и пользователь нажимает кнопку «OK». **DN_DEFAULTPRN** флаг установлен, если был установлен принтер по умолчанию. При выборе конкретного принтера не установлен флаг. Все биты в этом члене зарезервированы для внутреннего использования, процедура диалогового окна печати.  
  
## <a name="remarks"></a>Примечания  
 **PrintDlg** функция использует эти строки для инициализации членов в системные диалоговое окно печати. Когда пользователь закрывает диалоговое окно, возвращаются сведения о выбранном принтере в этой структуре.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** commdlg.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)



