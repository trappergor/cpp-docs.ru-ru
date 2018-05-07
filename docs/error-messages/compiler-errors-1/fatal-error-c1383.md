---
title: Неустранимая ошибка C1383 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae5e16959597e16f25320778be4d4b45ca5950e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1383"></a>Неустранимая ошибка C1383
Параметр компилятора /GL несовместим с установленной версией среды CRL  
  
 Ошибка C1383 происходит, когда вы используете предыдущую версию среды CLR с более новой версией компилятора и когда вы компилируете с параметрами **/clr** и **/GL.**  
  
 Для устранения этой ошибки не используйте параметры **/GL** и **/clr** или установите версию среды CLR, которая поставляется с вашим компилятором.  
  
 Дополнительные сведения см. в разделах [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) и [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).