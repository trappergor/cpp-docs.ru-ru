---
title: auto_inline | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
dev_langs:
- C++
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc2fb4cb870ff1dca2f0b55e9aad20741ffb8220
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083182"
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