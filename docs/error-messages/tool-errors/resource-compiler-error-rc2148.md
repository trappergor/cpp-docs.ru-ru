---
title: "Ошибка компилятора ресурсов RC2148 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2148
dev_langs:
- C++
helpviewer_keywords:
- RC2148
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee5add7bae569e08849ec7d3cb4f737c70ac97bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2148"></a>Ошибка компилятора ресурсов RC2148
ДИАЛЕКТЕ ID слишком велик  
  
 Значение идентификатора варианта языка находится за пределами допустимого диапазона.  
  
 Оператор **LANGUAGE** должен использовать следующий синтаксис:  
  
 **LANGUAGE** *ИД_основного_языка*,*ИД_дополнительного_языка*  
  
 Допустимые идентификаторы ДИАЛЕКТЕ определяются как **SUBLANG_** константы в файле WINNT.h.