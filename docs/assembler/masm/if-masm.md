---
title: IF (MASM) | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca0cce834924f7fc147b1ef301d5bd345dfd2973
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685311"
---
# <a name="if-masm"></a>IF (MASM)

Предоставляет сборку *ifstatements* Если *expression1* имеет значение true (ненулевое) или *elseifstatements* Если *expression1* имеет значение false (0) и *expression2* имеет значение true.

## <a name="syntax"></a>Синтаксис

> Если *expression1*<br/>
> *ifstatements*<br/>
> [[ELSEIF *expression2*<br/>
> *elseifstatements*]]<br/>
> [[ELSE<br/>
> *elsestatements*]]<br/>
> ENDIF

## <a name="remarks"></a>Примечания

Может заменить следующие директивы [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, и **ELSEIFNDEF** . При необходимости собирает *elsestatements* Если предыдущее выражение имеет значение false. Обратите внимание на то, что выражения вычисляются во время сборки.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>