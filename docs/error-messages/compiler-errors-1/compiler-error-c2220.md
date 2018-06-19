---
title: Ошибка компилятора C2220 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d23476de35e0af45b46a775683ba8673b4959346
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171497"
---
# <a name="compiler-error-c2220"></a>Ошибка компилятора C2220
Предупреждение, обрабатываемое как ошибка, объектный файл не создан  
  
 [/ WX](../../build/reference/compiler-option-warning-level.md) указывает компилятору обрабатывать все предупреждения как ошибки. Из-за ошибки, объект или исполняемый файл был создан.  
  
 Эта ошибка появляется, только когда **/WX** установлен флаг и возникновении предупреждения во время компиляции. Чтобы устранить эту ошибку, необходимо исключить каждое из них в проекте.  
  
### <a name="to-fix-use-one-of-the-following-techniques"></a>Чтобы устранить проблему, используйте один из следующих способов  
  
-   Устранение проблем, которые выводят предупреждения в проекте.  
  
-   На более низком уровне предупреждений компиляции — например, использовать **/W3** вместо **/W4**.  
  
-   Используйте [предупреждение](../../preprocessor/warning.md) pragma, чтобы отключить или запретить конкретное предупреждение.  
  
-   Не используйте **/WX** для компиляции.