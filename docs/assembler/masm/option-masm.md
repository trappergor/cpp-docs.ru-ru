---
title: ПАРАМЕТР (MASM) | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09db749baf09525957faaf8af99434cc9775d0e7
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678049"
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