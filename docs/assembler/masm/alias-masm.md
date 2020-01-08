---
title: ALIAS (MASM)
ms.date: 12/17/2019
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 5aef169c5632e74722438c63718ce5b783a8da09
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316607"
---
# <a name="alias"></a>ALIAS

Директива **Alias** создает альтернативное имя для функции.  Это позволяет создать несколько имен для функции или создать библиотеки, позволяющие компоновщику (LINK. exe) сопоставлять старую функцию с новой функцией.

## <a name="syntax"></a>Синтаксис

> Псевдоним **\<** _псевдоним_ **> = \<** _фактическое имя_ **>**

#### <a name="parameters"></a>Параметры

*фактическое имя*\
Фактическое имя функции или процедуры.  Угловые скобки являются обязательными.

*псевдоним*\
Альтернативное или имя псевдонима.  Угловые скобки являются обязательными.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
