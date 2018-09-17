---
title: Определение макроса NMAKE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c266a0be1c5ff16b719e9055f79b377d13ffbf3c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715719"
---
# <a name="defining-an-nmake-macro"></a>Определение макроса NMAKE

## <a name="syntax"></a>Синтаксис

```

macroname=string
```

## <a name="remarks"></a>Примечания

*Имя макроса* представляет собой сочетание букв, цифр и символов подчеркивания (_), не более 1024 символов, и происходит конфиденциальные. *Имя макроса* может содержать вызванный макрос. Если *имя макроса* состоит только из вызванного макроса, вызываемый макрос не может быть пустым или равным NULL.

`string` Может быть любой последовательностью из нуля или более символов. Пустая строка содержит нуль символов или только пробелы или символы табуляции. `string` Может содержать вызов макроса.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Специальные символы в макросах](../build/special-characters-in-macros.md)

[Пустой и неопределенный макрос](../build/null-and-undefined-macros.md)

[Где следует определять макросы](../build/where-to-define-macros.md)

[Приоритет в макроопределениях](../build/precedence-in-macro-definitions.md)

## <a name="see-also"></a>См. также

[Макросы и программа NMAKE](../build/macros-and-nmake.md)