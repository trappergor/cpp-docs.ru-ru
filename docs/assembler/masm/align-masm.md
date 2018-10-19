---
title: ВЫРАВНИВАНИЕ (MASM) | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- align
dev_langs:
- C++
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52d539cba3f6e00b76b36c1793f383d0615263c3
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691671"
---
# <a name="align-masm"></a>ALIGN (MASM)

Директива ALIGN сопровождается цифрой (X). 
Это число (X) должно быть степенью 2. То есть 2, 4, 8, 16 и так далее... 

Директива позволяет применять выравнивание инструкции или данных сразу после директивы для адреса памяти, кратного значению X. 

Дополнительное пространство между предыдущей инструкцией/данными и после директивы ALIGN дополняется инструкциями NULL (или эквивалентными инструкциями, такими как MOV EAX,EAX) в случае сегментов кода и null в случае сегментов данных.

Число X не может быть больше, чем выравнивание по умолчанию сегмента, на который ссылается директива ALIGN. Она должна быть меньше или равна выравниванию сегмента по умолчанию. .

## <a name="syntax"></a>Синтаксис

> ВЫРОВНЯТЬ [[*номер*]]

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
