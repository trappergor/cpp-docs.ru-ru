---
title: ALIAS (MASM) | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Alias
dev_langs:
- C++
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6a977d35040d8ca25cd3bd4ae4def233092b37a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691066"
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