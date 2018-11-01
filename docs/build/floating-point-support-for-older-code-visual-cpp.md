---
title: Поддержка плавающей запятой для устаревшего кода (Visual C++)
ms.date: 11/04/2016
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
ms.openlocfilehash: 2340a4d136dee3438a47ce06793ed9274035250d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509647"
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Поддержка плавающей запятой для устаревшего кода (Visual C++)

MMX и регистры с плавающей запятой стека (MM0-MM7/ST0-ST7) сохраняются на протяжении переключений контекста.  Отсутствует явное соглашение о вызовах для этих регистров.  Запрещено использование этих регистров в коде режима ядра.

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)