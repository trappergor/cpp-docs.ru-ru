---
title: Сигналы по умолчанию
ms.date: 11/04/2016
helpviewer_keywords:
- default signals
- defaults, signals
ms.assetid: db9fc17b-75c0-4d33-86be-c536584bbede
ms.openlocfilehash: 91d054f32a072f9ad9ebc15a8932bf2d52a43597
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647750"
---
# <a name="default-signals"></a>Сигналы по умолчанию

**ANSI 4.7.1.1** Если до вызова обработчика сигнала не выполняется эквивалент `signal(sig, SIG_DFL)`, сигнал блокируется.

В начале выполнения программы для сигналов задаются состояния по умолчанию.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)