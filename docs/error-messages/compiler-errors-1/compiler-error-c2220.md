---
title: "Ошибка компилятора C2220 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2220
dev_langs: C++
helpviewer_keywords: C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc31519b2153c66ea9bab42f536ba7c6be5b2a10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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