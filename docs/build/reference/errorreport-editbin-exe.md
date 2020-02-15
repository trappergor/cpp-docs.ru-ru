---
title: /ERRORREPORT (editbin.exe)
description: Справочник по параметру командной строки/ERRORREPORT программы Microsoft EDITBIN.
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
helpviewer_keywords:
- -ERRORREPORT editbin option
- ERRORREPORT editbin option
- /ERRORREPORT editbin option
ms.assetid: eca66ac3-b754-4bd7-9dd4-e04fc79a71b6
ms.openlocfilehash: 6c2ec8b6cda7b794114ed38cfb72b885bf2e38a1
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257602"
---
# <a name="errorreport-editbinexe"></a>/ERRORREPORT (editbin.exe)

> [!NOTE]
> Параметр/ERRORREPORT является устаревшим. Начиная с Windows Vista, Управление отчетами об ошибках осуществляется с помощью параметров [отчеты об ошибках Windows (WER)](/windows/win32/wer/windows-error-reporting) .

## <a name="syntax"></a>Синтаксис

> **/Errorreport** \[ **NONE** \| **Prompt** \| **очередь** \| **Send** ]

## <a name="remarks"></a>Примечания

Аргументы **/errorreport** переопределяются параметрами службы отчеты об ошибках Windows. Программа EDITBIN автоматически отправляет отчеты о внутренних ошибках в корпорацию Майкрософт, если отчетность включается отчеты об ошибках Windows. Если отключено отчеты об ошибках Windows, отчет не отправляется.

## <a name="see-also"></a>См. также:

[Параметры EDITBIN](editbin-options.md)
