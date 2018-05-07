---
title: Поддержка плавающей запятой для устаревшего кода (Visual C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd7cbf955fbf795d06d9cd2448d0736dc435f3b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Поддержка плавающей запятой для устаревшего кода (Visual C++)
MMX и регистры с плавающей запятой стека (MM0-MM7/ST0-ST7) сохраняются между переключений контекста.  Нет явного соглашение о вызовах для этих регистров.  Запрещено использование этих регистров в коде режима ядра.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)