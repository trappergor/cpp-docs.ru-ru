---
title: auto_inline
ms.date: 11/04/2016
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: c59dcc8ec7749a91565d5af043b1bd9e9eaa16ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403568"
---
# <a name="autoinline"></a>auto_inline
Исключает все функции, определенные в диапазоне где **off** задан, из числа кандидатов на автоматическое встроенное разворачивание.

## <a name="syntax"></a>Синтаксис

```
#pragma auto_inline( [{on | off}] )
```

## <a name="remarks"></a>Примечания

Чтобы использовать **auto_inline** pragma, поместите ее перед или сразу же после (не в) определение функции. Эта директива #pragma начинает действовать с первого определения функции после вхождения данной директивы.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)