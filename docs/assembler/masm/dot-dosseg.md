---
title: . DOSSEG | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33ee0b0b049ece65786c4d4857c2e082a067fee4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693236"
---
# <a name="dosseg"></a>.DOSSEG

Упорядочивает сегменты в соответствии с соглашением сегмент MS-DOS: код, во-первых, затем разделяет не в DGROUP и затем разделяет в DGROUP.

## <a name="syntax"></a>Синтаксис

> .DOSSEG

## <a name="remarks"></a>Примечания

Сегменты в DGROUP выполняйте в указанном порядке: сегменты не в BSS или СТЕК, а затем BSS сегментов и, наконец, сегменты стека. В основном используется для обеспечения поддержки CodeView в изолированных программ MASM. Совпадение с кодом [DOSSEG](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>