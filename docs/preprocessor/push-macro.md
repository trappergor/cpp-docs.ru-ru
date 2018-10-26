---
title: push_macro | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.push_macro
- push_macro_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, push_macro
- push_macro pragma
ms.assetid: ac89efc9-afd1-4dfe-bfd1-497229b3e81d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6a389289f8849ac6155543299392586dcd389d2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078951"
---
# <a name="pushmacro"></a>push_macro
Сохраняет значение *имени-макроса* вершине стека этого макроса.

## <a name="syntax"></a>Синтаксис

```
#pragma push_macro("
macro_name
")
```

## <a name="remarks"></a>Примечания

Можно получить значение для *имени-макроса* с `pop_macro`.

См. в разделе [pop_macro](../preprocessor/pop-macro.md) образец.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)