---
title: "Неустранимая ошибка C1107 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1107
dev_langs: C++
helpviewer_keywords: C1107
ms.assetid: 541a4d9f-10bc-4dd8-b68e-15e548f3dc0a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50a8524cdaddf3d160a2a718a1efbac2562f4127
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1107"></a>Неустранимая ошибка C1107
не удалось найти сборку «файл»: укажите путь поиска сборок с помощью /AI или путем установки переменной среды LIBPATH  
  
 Файл метаданных был передан [#using](../../preprocessor/hash-using-directive-cpp.md) директиву, компилятор не удалось найти.  
  
 Переменная среды LIBPATH, описанная в разделе, посвященном `#using`и [/AI](../../build/reference/ai-specify-metadata-directories.md) параметр компилятора позволяют указать каталоги, в которых компилятор будет искать файлы метаданных, на который указывает ссылка.