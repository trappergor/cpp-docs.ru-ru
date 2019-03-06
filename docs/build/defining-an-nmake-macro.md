---
title: Определение макроса NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: 6eb7c2f7759bda21f1424cef91b1dc814ba8d8ba
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424110"
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
