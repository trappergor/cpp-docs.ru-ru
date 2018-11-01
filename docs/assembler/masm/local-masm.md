---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c8ea49b9862159a5a56bfb3d2c3cd0c1f4cd7413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596876"
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