---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: a8215bf1f816baa490a768fb2cab0b3c2e53e20b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217261"
---
# <a name="option-masm"></a>OPTION (MASM)

Включает и выключает функции ассемблер.

## <a name="syntax"></a>Синтаксис

> ПАРАМЕТР *optionlist*

## <a name="remarks"></a>Примечания

Доступны следующие параметры.

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**ЭМУЛЯТОР**|
|**NOEMULATOR**|**ЭПИЛОГА**|**EXPR16**|**EXPR32**|
|**ЯЗЫК**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**СМЕЩЕНИЕ**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**ПРОЛОГ**|**ТОЛЬКО ДЛЯ ЧТЕНИЯ**|**NOREADONLY**|
|**ОБЛАСТЬЮ ДЕЙСТВИЯ**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|

Синтаксис языка **параметр языка:**<em>x</em>, где *x* является одним из C, SYSCALL, STDCALL, PASCAL, FORTRAN или BASIC.  SYSCALL, PASCAL, FORTRAN и BASIC не поддерживает с [. МОДЕЛЬ](../../assembler/masm/dot-model.md) ПЛОСКИМИ.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>