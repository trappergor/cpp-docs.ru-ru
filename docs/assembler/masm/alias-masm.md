---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 274ac451005015b2693d8674673af574ec781bdc
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399296"
---
# <a name="alias-masm"></a>ALIAS (MASM)

Директива **Alias** создает альтернативное имя для функции.  Это позволяет создать несколько имен для функции или создать библиотеки, позволяющие компоновщику (LINK. exe) сопоставлять старую функцию с новой функцией.

## <a name="syntax"></a>Синтаксис

> Псевдоним **\<** _псевдоним_ **> = \<** _фактическое имя_ **>**

#### <a name="parameters"></a>Параметры

*фактическое имя*\
Фактическое имя функции или процедуры.  Угловые скобки являются обязательными.

*псевдоним*\
Альтернативное или имя псевдонима.  Угловые скобки являются обязательными.

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
