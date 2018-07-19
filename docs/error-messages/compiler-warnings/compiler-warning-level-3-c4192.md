---
title: Предупреждение (уровень 3) C4192 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3bae9b7af95de94b8f667cb09710af21044f8b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291418"
---
# <a name="compiler-warning-level-3-c4192"></a>Предупреждение (уровень 3) C4192 компилятора
автоматически исключается 'name' при импорте библиотеки типов «библиотека»  
  
 Объект `#import` библиотека содержит элемент, *имя*, в котором также определены в системных заголовочных файлах Win32. Из-за ограничений библиотек типов, имена, такие как **IUnknown** или GUID часто определяются в библиотеках типов, дублирует определения системных заголовочных файлах. `#import` обнаружит эти элементы и не будет встраивать их в TLH-файлы и TLI-файлы.  
  
 Чтобы переопределить это поведение, используйте `#import` атрибуты [no_auto_exclude](../../preprocessor/no-auto-exclude.md) и [include()](../../preprocessor/include-parens.md).