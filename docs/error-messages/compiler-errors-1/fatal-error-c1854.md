---
title: "Неустранимая ошибка C1854 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1854
dev_langs:
- C++
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e0a26e902b1a40203bb4323bce8e28e687e9647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1854"></a>Неустранимая ошибка C1854
  
> Нельзя перезаписать данные, сформированные во время создания предкомпилированного заголовка в объектном файле: "*filename*"  
  
Вы указали [/Yu (использование предкомпилированных заголовков)](../../build/reference/yu-use-precompiled-header-file.md) параметр после указания [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md) вариант в том же файле.  
  
Чтобы устранить эту проблему, как правило, задать только один файл проекта, чтобы скомпилировать с помощью **/Yc** , а затем установить все файлы для компиляции с помощью **/Yu** параметр. Дополнительные сведения об использовании **/Yc** параметр, а также установите его в Интегрированной среде разработки Visual Studio см. в разделе [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md). Дополнительные сведения об использовании предкомпилированных заголовков см. в разделе [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md).  
