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
ms.openlocfilehash: dc1b8a3b8539fb4871e4a28f4635c8012b9f80a2
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538511"
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