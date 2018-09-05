---
title: ЛОКАЛЬНЫЙ (MASM) | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8105bc8168ce28d468a1378c5cf7889907a7c9f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685067"
---
# <a name="local-masm"></a>LOCAL (MASM)

В первой директиве макроса **ЛОКАЛЬНОГО** определяет метки, которые являются уникальными для каждого экземпляра макроса.

## <a name="syntax"></a>Синтаксис

> ЛОКАЛЬНЫЙ *localname* [[, *localname*]]...

> ЛОКАЛЬНЫЙ *метка* [[[*число*]]] [[:*тип*]] [[, *метка* [[[*число*]]] [[ *Тип*]]]]...

## <a name="remarks"></a>Примечания

В директиве второй в определении процедуры (**PROC**), **ЛОКАЛЬНОГО** создает переменные на основе стека, которые существуют во время процедуры. *Метка* может быть простой переменной или массив, содержащий *число* элементов.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>