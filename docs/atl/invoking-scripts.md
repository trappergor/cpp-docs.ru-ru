---
title: Вызов скриптов (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 6ca744ced53677550e7b77f44d4f6550da744372
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250471"
---
# <a name="invoking-scripts"></a>Вызов скриптов

[Использование подстановочных параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) рассматривается замена сопоставления и указан метод регистратора **AddReplacement**. Регистратор имеет восемь другие методы, определенные для сценариев, и все описаны в следующей таблице.

|Метод|Синтаксис и описание|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resFileName* **, целое число без знака** `nID` **, LPCOLESTR** `szType` **);**<br /><br /> Регистрирует скрипт, содержащийся в модуля ресурсов. *resFileName* указывает путь UNC к сам модуль. *nID* и *szType* содержат идентификатор ресурса и тип, соответственно.|
|**ResourceUnregister**|**HRESULT ResourceUnregister( LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType` **);**<br /><br /> Отменяет регистрацию скрипт, содержащийся в модуля ресурсов. *resFileName* указывает путь UNC к сам модуль. *nID* и *szType* содержат идентификатор ресурса и тип, соответственно.|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);**<br /><br /> Регистрирует скрипт, содержащийся в модуля ресурсов. *resFileName* указывает путь UNC к сам модуль. *szID* и *szType* содержат строковый идентификатор ресурса и тип, соответственно.|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);**<br /><br /> Отменяет регистрацию скрипт, содержащийся в модуля ресурсов. *resFileName* указывает путь UNC к сам модуль. *szID* и *szType* содержат строковый идентификатор ресурса и тип, соответственно.|
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR***fileName***);**<br /><br /> Регистрирует скрипт в файле. *Имя файла* является UNC-путь в файл, содержащий (или является) сценарий ресурсов.|
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR***fileName***);**<br /><br /> Отменяет регистрацию скрипта в файле. *Имя файла* является UNC-путь в файл, содержащий (или является) сценарий ресурсов.|
|**StringRegister**|**HRESULT StringRegister( LPCOLESTR**  *data*  **);**<br /><br /> Регистрирует скрипт в строке. *данные* содержит самого сценария.|
|**StringUnregister**|**HRESULT StringUnregister( LPCOLESTR**  *data*  **);**<br /><br /> Отменяет регистрацию сценария в строке. *данные* содержит самого сценария.|

**ResourceRegisterSz** и **ResourceUnregisterSz**, аналогичны **ResourceRegister** и **ResourceUnregister**, но позволяет указать строку идентификатор.

Методы **FileRegister** и **FileUnregister** полезны, если не требуется, скрипт в виде ресурса, или если требуется, скрипт в отдельном файле. Методы **StringRegister** и **StringUnregister** разрешить RGS-файл для сохранения в динамически выделяемый строка.

## <a name="see-also"></a>См. также

[Создание скриптов регистратора](../atl/creating-registrar-scripts.md)
