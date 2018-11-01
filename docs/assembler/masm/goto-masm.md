---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: a03cbda5a8ff64f6c167766f416e7744a5382ad5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654684"
---
# <a name="goto-masm"></a>GOTO (MASM)

Передает строку, помеченную сборки **:**_macrolabel_.

## <a name="syntax"></a>Синтаксис

> **GOTO** *macrolabel*

## <a name="remarks"></a>Примечания

**GOTO** разрешены только в [МАКРОС](macro.md), [для](for-masm.md), [принудительное Включение](forc.md), [ПОВТОРИТЕ](repeat.md), и [при](while-masm.md)блоков. *Macrolabel* целевой объект должен быть единственным директивы в той строке и должен предшествовать начальное двоеточие.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
