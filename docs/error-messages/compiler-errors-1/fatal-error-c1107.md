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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c8cf4371b7409fb01f6000eb5abccefc22fcdf21
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1107"></a>Неустранимая ошибка C1107
не удалось найти сборку «файл»: необходимо указать путь поиска сборок с помощью /AI или путем установки переменной среды LIBPATH  
  
 Файл метаданных передан [#using](../../preprocessor/hash-using-directive-cpp.md) директивы, компилятору не удается найти.  
  
 Переменная среды LIBPATH, описанная в разделе, посвященном `#using`и [/AI](../../build/reference/ai-specify-metadata-directories.md) параметр компилятора позволяют указать каталоги, в которых компилятор будет искать файлы метаданных, на который указывает ссылка.
