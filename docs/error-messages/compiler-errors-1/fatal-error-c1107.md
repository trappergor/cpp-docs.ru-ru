---
title: "Неустранимая ошибка C1107 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1107
dev_langs:
- C++
helpviewer_keywords:
- C1107
ms.assetid: 541a4d9f-10bc-4dd8-b68e-15e548f3dc0a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7746c880b251eccfa1d2688d3ab91b7893970f5c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1107"></a>Неустранимая ошибка C1107
не удалось найти сборку «файл»: укажите путь поиска сборок с помощью /AI или путем установки переменной среды LIBPATH  
  
 Файл метаданных был передан [#using](../../preprocessor/hash-using-directive-cpp.md) директиву, компилятор не удалось найти.  
  
 Переменная среды LIBPATH, описанная в разделе, посвященном `#using`и [/AI](../../build/reference/ai-specify-metadata-directories.md) параметр компилятора позволяют указать каталоги, в которых компилятор будет искать файлы метаданных, на который указывает ссылка.
