---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: ab00092f410d34119e876db4562e6d0709743d79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483503"
---
# <a name="alias-masm"></a>ALIAS (MASM)

**ПСЕВДОНИМ** директива создает альтернативное имя для функции.  Это позволяет создать несколько имен для функции или библиотеки, которые позволяют компоновщик (LINK.exe) для сопоставления старые функции в новую функцию.

## <a name="syntax"></a>Синтаксис

> ПСЕВДОНИМ \< *псевдоним*> = \< *фактическое имя*>

#### <a name="parameters"></a>Параметры

*Фактическое имя*<br/>
Фактическое имя функции или процедуры.  Угловые скобки являются обязательными.

*alias*<br/>
Имя альтернативного или псевдоним.  Угловые скобки являются обязательными.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>