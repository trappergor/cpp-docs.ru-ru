---
title: GOTO (MASM) | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0be678e2d39389cbc551c386c1890f799124b5b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43694005"
---
# <a name="goto-masm"></a>GOTO (MASM)

Передает строку, помеченную сборки **:**_macrolabel_.

## <a name="syntax"></a>Синтаксис

> **GOTO** *macrolabel*

## <a name="remarks"></a>Примечания

**GOTO** разрешены только в [МАКРОС](macro.md), [для](for-masm.md), [принудительное Включение](forc.md), [ПОВТОРИТЕ](repeat.md), и [при](while-masm.md)блоков. *Macrolabel* целевой объект должен быть единственным директивы в той строке и должен предшествовать начальное двоеточие.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
