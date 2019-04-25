---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: ab00092f410d34119e876db4562e6d0709743d79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166494"
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