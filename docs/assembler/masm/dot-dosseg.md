---
title: .DOSSEG
ms.date: 08/30/2018
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 28b3e351030ee83693c0fec5568aacf9b4b77c27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204365"
---
# <a name="dosseg"></a>.DOSSEG

Упорядочивает сегменты в соответствии с соглашением MS-DOS сегмент: Во-первых, код затем разделяет не в DGROUP и затем разделяет в DGROUP.

## <a name="syntax"></a>Синтаксис

> .DOSSEG

## <a name="remarks"></a>Примечания

Сегменты в DGROUP выполняйте в указанном порядке: сегменты не в BSS или СТЕК, а затем BSS сегментов и, наконец, сегменты стека. В основном используется для обеспечения поддержки CodeView в изолированных программ MASM. Совпадение с кодом [DOSSEG](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>