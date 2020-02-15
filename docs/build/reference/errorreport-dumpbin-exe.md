---
title: /ERRORREPORT (dumpbin.exe)
description: Ссылка на параметр командной строки Microsoft DUMPBIN Utility/ERRORREPORT.
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
helpviewer_keywords:
- -ERRORREPORT dumpbin option
- ERRORREPORT dumpbin option
- /ERRORREPORT dumpbin option
ms.assetid: 51178c43-4f95-4fda-8f97-50a257d1c948
ms.openlocfilehash: 665b4b1e7c01de4a1fcd848a9e6b36ddbf2944c9
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257680"
---
# <a name="errorreport-dumpbinexe"></a>/ERRORREPORT (dumpbin.exe)

> [!NOTE]
> Параметр/ERRORREPORT является устаревшим. Начиная с Windows Vista, Управление отчетами об ошибках осуществляется с помощью параметров [отчеты об ошибках Windows (WER)](/windows/win32/wer/windows-error-reporting) .

## <a name="syntax"></a>Синтаксис

> **/Errorreport**\[**NONE** \| **Prompt** \| **очередь** \| **Send** ]

## <a name="remarks"></a>Примечания

Аргументы **/errorreport** переопределяются параметрами службы отчеты об ошибках Windows. Программа DUMPBIN автоматически отправляет отчеты о внутренних ошибках в корпорацию Майкрософт, если отчетность включается отчеты об ошибках Windows. Если отключено отчеты об ошибках Windows, отчет не отправляется.

## <a name="see-also"></a>См. также:

[Параметры DUMPBIN](dumpbin-options.md)
