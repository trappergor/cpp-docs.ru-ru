---
title: Неустранимая ошибка C1107 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1107
dev_langs:
- C++
helpviewer_keywords:
- C1107
ms.assetid: 541a4d9f-10bc-4dd8-b68e-15e548f3dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 949ee09244a106984522fb35dd13c0b3426fc820
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1107"></a>Неустранимая ошибка C1107
не удалось найти сборку «файл»: укажите путь поиска сборок с помощью /AI или путем установки переменной среды LIBPATH  
  
 Файл метаданных был передан [#using](../../preprocessor/hash-using-directive-cpp.md) директиву, компилятор не удалось найти.  
  
 Переменная среды LIBPATH, описанная в разделе, посвященном `#using`и [/AI](../../build/reference/ai-specify-metadata-directories.md) параметр компилятора позволяют указать каталоги, в которых компилятор будет искать файлы метаданных, на который указывает ссылка.