---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 94af498865151ff5c49fac9dbc03de65c4ecb934
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327607"
---
# <a name="local-masm"></a>LOCAL (MASM)

В первой директиве макроса **ЛОКАЛЬНОГО** определяет метки, которые являются уникальными для каждого экземпляра макроса.

## <a name="syntax"></a>Синтаксис

> ЛОКАЛЬНЫЙ *localname* \[, *localname*]...
>
> ЛОКАЛЬНЫЙ *метка* \[ __\[__ *число*__]__ ] \[ __:__  *Тип*] \[ __,__ *метка* \[ __\[__ *число* __]__  ] \[ *тип*]]...

## <a name="remarks"></a>Примечания

В директиве второй в определении процедуры (**PROC**), **ЛОКАЛЬНОГО** создает переменные на основе стека, которые существуют во время процедуры. *Метка* может быть простой переменной или массив, содержащий *число* элементов.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>