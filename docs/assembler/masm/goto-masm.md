---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: a03cbda5a8ff64f6c167766f416e7744a5382ad5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203090"
---
# <a name="goto-masm"></a>GOTO (MASM)

Передает строку, помеченную сборки **:**_macrolabel_.

## <a name="syntax"></a>Синтаксис

> **GOTO** *macrolabel*

## <a name="remarks"></a>Примечания

**GOTO** разрешены только в [МАКРОС](macro.md), [для](for-masm.md), [принудительное Включение](forc.md), [ПОВТОРИТЕ](repeat.md), и [при](while-masm.md)блоков. *Macrolabel* целевой объект должен быть единственным директивы в той строке и должен предшествовать начальное двоеточие.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
