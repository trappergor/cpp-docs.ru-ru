---
title: Сигналы по умолчанию
ms.date: 11/04/2016
helpviewer_keywords:
- default signals
- defaults, signals
ms.assetid: db9fc17b-75c0-4d33-86be-c536584bbede
ms.openlocfilehash: bb84e168d0693313373395e8d5f44be0eca9891e
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152564"
---
# <a name="default-signals"></a>Сигналы по умолчанию

**ANSI 4.7.1.1** Если до вызова обработчика сигнала не выполняется эквивалент `signal(sig, SIG_DFL)`, сигнал блокируется.

В начале выполнения программы для сигналов задаются состояния по умолчанию.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)
